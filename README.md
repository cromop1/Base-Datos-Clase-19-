# 🗄️ Constraints & Triggers — MySQL

![MySQL](https://img.shields.io/badge/MySQL-8.0-4479A1?style=for-the-badge\&logo=mysql\&logoColor=white)
![SQL](https://img.shields.io/badge/SQL-Database-orange?style=for-the-badge)
![Sakila](https://img.shields.io/badge/Database-Sakila-blueviolet?style=for-the-badge)
![Status](https://img.shields.io/badge/Status-Completed-success?style=for-the-badge)
![Academic](https://img.shields.io/badge/Project-Academic-informational?style=for-the-badge)

---

## 📌 Descripción

Proyecto práctico de **Bases de Datos** enfocado en el uso de:

* Constraints
* Primary Keys
* Foreign Keys
* `CHECK`
* `NOT NULL`
* Integridad referencial
* Triggers
* Auditoría de modificaciones
* Base de datos Sakila

El objetivo principal es comprender cómo MySQL permite mantener la integridad y consistencia de los datos mediante restricciones y automatizaciones.

---

## 🛠️ Tecnologías

| Tecnología      | Uso                                        |
| --------------- | ------------------------------------------ |
| MySQL           | Motor de base de datos                     |
| SQL             | Consultas y manipulación de datos          |
| Sakila          | Base de datos de práctica                  |
| MySQL Workbench | Administración y ejecución de consultas    |
| DBeaver         | Alternativa para gestión de bases de datos |

---

## 📚 Actividades

### Act 1 — `NOT NULL`

```sql
-- Act 1

INSERT INTO employees
(employeeNumber, lastName, firstName, extension, email, officeCode, reportsTo, jobTitle)
VALUES
(1800, 'Segura', 'Bruno', 'x9999', NULL, '1', 1002, 'Developer');
```

---

### Act 2 — Actualización de Primary Key

```sql
-- Act 2

UPDATE employees
SET employeeNumber = employeeNumber - 20;

UPDATE employees
SET employeeNumber = employeeNumber + 20;
```

---

### Act 3 — Restricción de edad

```sql
-- Act 3

ALTER TABLE employees
ADD age INT CHECK (age BETWEEN 16 AND 70);
```

---

### Act 4 — Integridad referencial

```sql
-- Act 4

SHOW CREATE TABLE sakila.film_actor;
```

---

### Act 5 — Trigger de actualización

```sql
-- Act 5

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
```

---

### Act 6 — Triggers de Sakila

```sql
-- Act 6

SHOW TRIGGERS FROM sakila
WHERE `Table` = 'film';
```

---

## 🧠 Conceptos trabajados

```text
Constraints
   │
   ├── NOT NULL
   ├── CHECK
   ├── PRIMARY KEY
   └── FOREIGN KEY

Triggers
   │
   ├── BEFORE INSERT
   ├── BEFORE UPDATE
   ├── AFTER INSERT
   ├── AFTER UPDATE
   └── AFTER DELETE
```

---

## 🗃️ Base de datos utilizada

Se utilizó principalmente:

```text
ClassicModels
Sakila
```

Sakila es una base de datos de ejemplo utilizada para practicar relaciones, consultas, procedimientos y triggers en MySQL.

---

## 🔗 Recursos

[![MySQL Docs](https://img.shields.io/badge/MySQL-Documentation-4479A1?style=flat-square\&logo=mysql\&logoColor=white)](https://dev.mysql.com/doc/)

[![Sakila](https://img.shields.io/badge/Sakila-Documentation-blueviolet?style=flat-square\&logo=mysql\&logoColor=white)](https://dev.mysql.com/doc/sakila/en/)

[![DBeaver](https://img.shields.io/badge/DBeaver-Database_Manager-382923?style=flat-square)](https://dbeaver.io/)

[![GitHub](https://img.shields.io/badge/GitHub-Repository-181717?style=flat-square\&logo=github\&logoColor=white)](https://github.com/)

---

## 👨‍💻 Autor

**Bruno Ángel Segura Marsal**

![Backend](https://img.shields.io/badge/Backend-Developer-black?style=flat-square)
![Cybersecurity](https://img.shields.io/badge/Cybersecurity-Student-red?style=flat-square)
![Python](https://img.shields.io/badge/Python-Developer-3776AB?style=flat-square\&logo=python\&logoColor=white)
![Django](https://img.shields.io/badge/Django-Developer-092E20?style=flat-square\&logo=django\&logoColor=white)

---

<p align="center">
  <b>Base de Datos · Constraints · Triggers · MySQL</b>
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Made%20with-MySQL-4479A1?style=for-the-badge&logo=mysql&logoColor=white">
</p>
**
