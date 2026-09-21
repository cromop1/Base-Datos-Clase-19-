-- Act 1:
INSERT INTO employees
(employeeNumber, lastName, firstName, extension, email, officeCode, reportsTo,
    jobTitle)
VALUES
(1800, 'Segura', 'Bruno', 'x9999', NULL, '1', 1002, 'Developer');



-- Act 2:
UPDATE employees
SET employeeNumber = employeeNumber - 20;
UPDATE employees
SET employeeNumber = employeeNumber + 20;


-- Act 3:
ALTER TABLE employees
ADD age INT CHECK (age BETWEEN 16 AND 70);


-- Act 4:
SHOW CREATE TABLE sakila.film_actor;




-- Act 5:
ALTER TABLE employees
ADD lastUpdate DATETIME,
ADD lastUpdateUser VARCHAR(100);
DELIMITER $$
CREATE TRIGGER employees_before_insert
BEFORE INSERT ON employees
FOR EACH ROW
BEGIN
SET NEW.lastUpdate = NOW();
SET NEW.lastUpdateUser = USER();
END$$
CREATE TRIGGER employees_before_update
BEFORE UPDATE ON employees
FOR EACH ROW
BEGIN
SET NEW.lastUpdate = NOW();
SET NEW.lastUpdateUser = USER();
END$$
DELIMITER ;



-- Act 6:
SHOW TRIGGERS FROM sakila
WHERE `Table` = 'film';