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
|---------------------------|-------|------|-------|
| Automatic Value equality? | ✅ | ❌ |✅|
| Immutable                 | ✅ | ❌ |✅|
| Memory Allocation         | Heap | Heap | Stack (faster) |



## Primary Constructors for Records vs Classes

|Feature|Record|Class|Struct|
|-------|-------|-------|-------|
|Members Exposed Automatically? | ✅ |❌ |✅ |
|Equality By Value? | ✅ | ❌ ||✅ |


## CollectionExpressions


##### Before
```csharp
int[] a = new int[] ｛1, 2, 3, 4, 5, 6,7,8｝；
 // or
var a = new int[] { 1, 2, 3, 4, 5, 6, 7, 8};
```

##### After
```csharp
int[] a = [1, 25 3, 4, 5, 6, 7, 8];
// cant use var
//var a2 = [1, 25 3, 4, 5, 6, 7, 8];
```


## Type Aliases

##### Before

```csharp
public class Square
{
    public (int X, int Y, int Width, int Height) GetBoundaries() => new (X, Y, Width, Height);
    public void SetBoundaries((int X, int Y, int Width, int Height) boundaries) { .... }
}
```

##### After

```csharp
using Boundaries = (int X, int Y, int Width, int Height);
public class Square
{
public Boundaries GetBoundaries()
=> new (X, Y, Width, Height);
public void SetBoundaries(Boundaries boundaries) { .... }
}

```




