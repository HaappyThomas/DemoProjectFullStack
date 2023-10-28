# DemoProjectFullStack
[En]:This is a simple Full Stack demo project.

[Fr]:Il s'agit d'un simple projet de démonstration Full Stack.

# Objectif:
  [En]: I develop a simple Full Stack demo project for demonstrate how it works frontend and backend separated.
  
  [Fr]: Je développe un projet de démonstration Full Stack simple pour démontrer comment il fonctionne séparément du frontend et du backend.

# Description
  [En]: This project is for manager the employees of an enterprise. 
        Add, retrieve, modify, delete and retrieve by keyword(CRUD) the employee.
        
  [Fr]: Ce projet s'adresse aux managers des salariés des entreprises.
        Ajoutez, récupérez, modifiez, supprimez et récupérez par mot-clé (CRUD) le salarié.

# Tech stack
  ## front end
     - Framework: Angular
     - IDE: VS Code
  ## Back end
     - .Net core 6.0, C#
     - IDE: Visual Studio
     - Database: MySQL.
# Back end architect   

# Database:
   1.Table: 
     - Employees (No, FirstName, LastName, Birthday, Position, Niveau, Salary, RetirementDate)
     - Parameters (Id, Position, WorkYears)
     - Niveaux (Id, Niveau)
     - Positions (Id, Position)
     
   2. Script SQL to create database(fullstackdemo), tables and insert values into the tables in MySQL
      
    2.1 Create database fullstackdemo in MySQL
        - CREATE SCHEMA `fullstackdemo` ;
        
    2.2 Create the tables 
        - CREATE TABLE `fullstackdemo`.`employees` (
          `No` INT NOT NULL AUTO_INCREMENT,
          `FirstName` VARCHAR(20) NULL,
          `LastName` VARCHAR(30) NULL,
          `Birthday` DATE NULL,
          `Position` VARCHAR(45) NULL,
          `Niveau` INT NULL,
          `Salary` DECIMAL(12) NULL,
          `RetirementDate` DATE NULL,
          PRIMARY KEY (`No`),
          UNIQUE INDEX `No_UNIQUE` (`No` ASC) VISIBLE);
          
        - CREATE TABLE `fullstackdemo`.`parameters` (
          `Id` INT NOT NULL AUTO_INCREMENT,
          `Position` VARCHAR(45) NULL,
          `WorkYears` INT NULL,
          PRIMARY KEY (`Id`));

        - CREATE TABLE `fullstackdemo`.`niveaux` (
          `Niveau` INT NOT NULL,
          PRIMARY KEY (`Niveau`),
          UNIQUE INDEX `Niveau_UNIQUE` (`Niveau` ASC) VISIBLE);

        - CREATE TABLE `fullstackdemo`.`positions` (
          `Position` VARCHAR(45) NOT NULL,
          PRIMARY KEY (`Position`),
          UNIQUE INDEX `Position_UNIQUE` (`Position` ASC) VISIBLE);

      2.3 Create relationship
      
        - ALTER TABLE `fullstackdemo`.`employees`
  ADD CONSTRAINT FK_Employees_Niveaux FOREIGN KEY(Niveau) REFERENCES  niveaux(Niveau);
        - ALTER TABLE `fullstackdemo`.`employees`
  ADD CONSTRAINT FK_Employees_Types FOREIGN KEY(Position) REFERENCES  positions(Position);  
        - ALTER TABLE `fullstackdemo`.`parameters`
  ADD CONSTRAINT FK_Parameter_Positions FOREIGN KEY(Position) REFERENCES  positions(Position);

      2.4 Insert values
        - 


