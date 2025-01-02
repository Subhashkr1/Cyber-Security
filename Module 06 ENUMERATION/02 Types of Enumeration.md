# Types of Enumeration

Enumerations (enums) come in various forms depending on the programming language and its features. Below are common types of enumerations and their characteristics.

## 1. Simple Enumeration

### Definition

A simple enumeration defines a set of named constants, typically represented by integer values starting from zero by default.

### Example

**C/C++:**

```c
enum Day {
    SUNDAY,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
};
```

Java:

```java
public enum Day {
    SUNDAY,
    MONDAY,
    TUESDAY,
    WEDNESDAY,
    THURSDAY,
    FRIDAY,
    SATURDAY
}
```
Python:

```python
from enum import Enum

class Day(Enum):
    SUNDAY = 1
    MONDAY = 2
    TUESDAY = 3
    WEDNESDAY = 4
    THURSDAY = 5
    FRIDAY = 6
    SATURDAY = 7
```

## 2. String Enumeration
**Definition**

A string enumeration associates each named constant with a specific string value, which can be more descriptive than simple numeric values.

Example
Java:

```java
public enum Status {
    PENDING("Pending"),
    IN_PROGRESS("In Progress"),
    COMPLETED("Completed");

    private final String displayName;

    Status(String displayName) {
        this.displayName = displayName;
    }

    public String getDisplayName() {
        return displayName;
    }
}
```
Python:

```python
from enum import Enum

class Status(Enum):
    PENDING = "Pending"
    IN_PROGRESS = "In Progress"
    COMPLETED = "Completed"
```

## 3. Flags Enumeration
Definition
Flags enumeration uses bitwise operations to represent a combination of options. Each value in the enumeration corresponds to a bit flag.

Example
C/C++:

```c

enum Permissions {
    READ = 1 << 0,    // 0001
    WRITE = 1 << 1,   // 0010
    EXECUTE = 1 << 2  // 0100
};

int userPermissions = READ | WRITE; // User can read and write
```
C#:

```csharp

[Flags]
public enum Permissions {
    None = 0,
    Read = 1 << 0,
    Write = 1 << 1,
    Execute = 1 << 2
}

Permissions userPermissions = Permissions.Read | Permissions.Write; // User can read and write
```
## 4. Extended Enumeration
**Definition**

Extended enumerations provide additional methods or properties that enhance their functionality beyond basic enumerator values.

Example

Java:

```java
public enum Operation {
    ADDITION {
        @Override
        public double apply(double a, double b) {
            return a + b;
        }
    },
    SUBTRACTION {
        @Override
        public double apply(double a, double b) {
            return a - b;
        }
    };

    public abstract double apply(double a, double b);
}
```
Python:

```python
from enum import Enum

class Operation(Enum):
    ADDITION = lambda a, b: a + b
    SUBTRACTION = lambda a, b: a - b

    def apply(self, a, b):
        return self.value(a, b)
```

**Conclusion**

Different types of enumerations offer various functionalities and use cases, from simple constant sets to more complex flag combinations and extended functionalities. Understanding these types allows programmers to choose the most suitable form of enumeration based on their needs.