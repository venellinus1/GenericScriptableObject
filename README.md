# GenericScriptableObject
```csharp
using UnityEngine;
/// <summary>
/// example for scriptable object with generics, workaround for ScriptableObjectGenerics<T> not possible with scriptable objects
/// </summary>
[CreateAssetMenu(fileName = "EventKey", menuName = "EventSystem/GenericScriptableObject")]
public class GenericScriptableObject : ScriptableObject
{

    System.Object obj;

    public void Set<T>(T obj) where T : class
    {
        this.obj = obj;
    }

    public T Get<T>() where T : class
    {
        return (T)obj;
    }

    public void Set(System.Object obj)
    {
        this.obj = obj;
    }

    public System.Object Get()
    {
        return obj;
    }
}
