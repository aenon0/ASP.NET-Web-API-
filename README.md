------TABLE DEFENITION IN SQL

CREATE TABLE TestEmployee(Id INT IDENTITY(1,1) PRIMARY KEY, @Name VARCHAR(100), @Age INT, @Active INT);


------STORED PROCEDURES IN SQL

--proc to add employee
CREATE PROC usp_AddEmployee(@Name VARCHAR(100), @Age INT, @Active INT)
AS
BEGIN
	INSERT INTO TestEmployee(Name, Age, Active)
	VALUES(@Name, @Age, @Active);
END

--proc to select all employees
CREATE PROC usp_GetAllEmployees
AS
BEGIN 
	SELECT * FROM TestEmployee;
END

--proc to select a single employee by id
CREATE PROC usp_GetEmployeeById(@Id INT)
AS
BEGIN
	SELECT * FROM TestEmployee WHERE Id = @Id;
END

--proc to update employee
CREATE PROC usp_UpdateEmployee(@Id INT, @Name VARCHAR(100), @Age INT, @Active INT)
AS
BEGIN
	UPDATE TestEmployee 
	SET Name = @Name, Age = @Age, Active = @Active
	WHERE Id = @Id;
END

--proc to delete employee
CREATE PROC usp_DeleteEmployee(@Id INT)
AS 
BEGIN 
	DELETE FROM  TestEmployee where Id = @Id;
END

--use this link for more: https://youtu.be/DboyInxNgXc

