using Microsoft.EntityFrameworkCore;

namespace ConsoleApp1
{
    public class ApplicationContext:DbContext
    {
        public DbSet<User> Users { get; set; } = null!;
        public DbSet<Company> Companies { get; set; } = null!;
        public DbSet<Country> Countries { get; set; } = null!;

        protected override void OnConfiguring(DbContextOptionsBuilder optionsBuilder )
        {
            optionsBuilder.UseNpgsql( "Host=localhost; Port=5432; Database=EagerLoading; Username =postgres; Password=1234");
        }
    }
}
