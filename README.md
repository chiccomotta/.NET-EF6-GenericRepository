.NET-EF6-GenericRepository
==========================

A Generic Entity Framework 6 data repository for .NET 4.5 supporting both sync and async methods

#NOTA: modificato da me per .NET CORE 2.0

#Usage
Include the BaseRepository.cs class in your application and set the appropriate namespace.

Inherit from BaseRepository in your Service classes and initialize the constructor and base constructor with a data context.

```C#
public class CategoryRepository : BaseRepository<Category>
{
    public CategoryService(MyDataContext context)
        : base(context)
    { }
}
```

#Overrides
Override the base methods as needed by declaring the same method as *new*

```C#
public new async Task<Category> GetAsync(int id)
{
    return await _context.Categories.SingleOrDefaultAsync(x => x.categoryID == id);
}
```
