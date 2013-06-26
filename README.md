Huey
====

A data access library for .NET


Goals
=====

- Needs to be fast. Like "Dapper" fast.
- Easy to use. Nice predictable API.
- Validatable SQL in the build process.
- Target MS SQL Server 2012.
- Intellisense for composing SQL queries.

Usage Examples
==============

(Brainstorming - wont compile...)

'''Sql
-- [Name(GetByMake)]
-- [Namespace(Cars)]
-- [Description(Get all cars by a specific make)]
SELECT C.Id, M.Name AS Make, C.Model
FROM Car C
INNER JOIN Make M ON C.MakeId = M.Id
WHERE M.Name = @make
'''

'''Csharp
public partial class CarsQueries
{
  private static string getByMakeSql = "";

  public List<Car> GetByMake(string make)
  {  
    ...
  }
'''

'''Csharp
var cars = connection.Cars.GetByMake("BMW");
'''

