```sql
select Owners.City, SUM(Procedures.Price) as TotalSales
From Sales 
Left Join Procedures On Sales.ProcedureCode = Procedures.ProcedureCode
Left Join Pets on Sales.PetID = Pets.PetID
Left Join Owners on Pets.OwnerID = Owners.OwnerID
group by Owners.City
Order by TotalSales Desc;
```
```sql
select Pets.Kind, SUM(Procedures.Price) as TotalSales
From Sales 
Left Join Procedures On Sales.ProcedureCode = Procedures.ProcedureCode
Left Join Pets on Sales.PetID = Pets.PetID
Left Join Owners on Pets.OwnerID = Owners.OwnerID
group by Pets.Kind
Order by TotalSales Desc;
```
```sql
SELECT Owners.City, Pets.Kind,  SUM(Procedures.Price) AS TotalSales
FROM Owners
LEFT JOIN Pets ON Pets.OwnerID = Owners.OwnerID
LEFT JOIN Sales ON Pets.PetID = Sales.PetID
LEFT JOIN Procedures ON Sales.ProcedureCode =Procedures.ProcedureCode
GROUP BY Owners.City, Pets.Kind
ORDER by Owners.City;
```
```sql
select Owners.City, ROUND(AVG(Procedures.Price),2) as AverageSales
From Sales 
Left Join Procedures On Sales.ProcedureCode = Procedures.ProcedureCode
Left Join Pets on Sales.PetID = Pets.PetID
Left Join Owners on Pets.OwnerID = Owners.OwnerID
group by Owners.City
Order by AverageSales;
```
```sql
SELECT Owners.City, Pets.Kind,  AVG(Procedures.Price) AS AvgSalesByCity
FROM Sales
LEFT JOIN Pets ON Sales.PetID = Pets.PetID
LEFT JOIN Owners ON Pets.OwnerID = Owners.OwnerID
LEFT JOIN Procedures ON Sales.ProcedureCode = Procedures.ProcedureCode
GROUP BY Owners.City, Pets.Kind
ORDER BY AvgSalesByCity DESC;
```
