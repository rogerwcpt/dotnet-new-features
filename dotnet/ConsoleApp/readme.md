# What's new in C# 12

## Primary Constructors

##### Before

```csharp
public class User
{
    // With Explicit Constructor 
    public User(string userName, string fullName)
    {
        UserName = userName;
        FullName = fullName;
    }
    
    public string UserName { get; }
    public string FullName { get; }
}

```

#### After (C# 12)

```csharp

// With Primary Constructor
public class UserClass(string userName, string fullName)
{
    public string UserName { get; } = userName;
    public string FullName { get; } = fullName;
}
```

#### Records (C# 9)

```chsarp

public record User(string UserName, string FullName);
```


##  Records vs Classes

| Feature                   |Record|Class|Struct|
|---------------------------|-------|-------|-------|
| Automatic Value equality? | ✅ | ❎ |✅|
| Immutable                 | ✅ | ❎ |✅|
| Memory Allocation         | Heap | Heap | Stack (faster) |



## Primary Constructors for Records vs Classes

|Feature|Record|Class|Struct|
|-------|-------|-------|-------|
|Members Exposed Automatically? | ✅ | ❎ |✅ |
|Equality By Value? | ✅ | ❎ ||✅ |


## Type Aliases

##### Before

```csharp
public class Square
{
    public (int X, int Y, int Width, int Height) GetBoundaries() => new (X, Y, Width, Height);
    public void SetBoundaries((int X, int Y, int Width, int Height) boundaries) { .... }
}
```

##### Before

```csharp
using Boundaries = (int X, int Y, int Width, int Height);
public class Square
{
public Boundaries GetBoundaries()
=> new (X, Y, Width, Height);
public void SetBoundaries(Boundaries boundaries) { .... }
}

```




