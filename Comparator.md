# Comparator Interface

- Collections.sort(employees,Comparator.comparing(e-> e.id));  

- students.sort(Comparator.comparing(s -> s.name));  


- students.sort(Comparator.comparing(Student::getName));  
public String getName() {
    return name;
}


### Multiple Field Sorting (Chaining) Sort by name, then by id:
students.sort(
    Comparator.comparing(Student::getName)
              .thenComparing(Student::getId)
);

###  null handling   
students.sort(
    Comparator.comparing(Student::getName,
        Comparator.nullsFirst(String::compareTo))
);
