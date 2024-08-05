# Usage
In this document, you will find how to use `commons-sql` in your project.

### Example
```Java
package com.example;

import com.zaxxer.hikari.HikariConfig;
import pl.mrstudios.commons.sql.SqlConnection;

import java.util.Collection;

import static pl.mrstudios.commons.sql.statement.SqlStatement.createStatement;

public class Example {

    private final HikariConfig hikariConfig;
    private final SqlConnection sqlConnection;

    private final Collection<Employee> employees;

    public Example() {

        this.hikariConfig = new HikariConfig();
        this.hikariConfig.setJdbcUrl("jdbc:mysql://localhost:3306/database");
        this.hikariConfig.setUsername("admin");
        this.hikariConfig.setPassword("password");

        this.sqlConnection = new SqlConnection(this.hikariConfig);
        this.employees = createStatement("SELECT * FROM employs WHERE group=?;")
                .setString(1, "janitor")
                .fetch(this.sqlConnection)
                .stream()
                .map((row) -> {

                    Employee employee = new Employee();

                    employee.name = row.entry("name").asString();
                    employee.surname = row.entry("surname").asString();
                    employee.group = row.entry("group").asString();
                    employee.salary = row.entry("salary").asInteger();

                    return employee;

                }).toList();

    }

    static class Employee {
        public String name;
        public String surname;
        public String group;
        public int salary;
    }

}
```