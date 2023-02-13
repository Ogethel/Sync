

## Runtime Sets

### Scriptable Object Component Script
```C#
public abstract class RuntimeSet<T> : ScriptableObject
{
	public List<T> Items = new List<T>();
	
	public void Add(T t)
	{
		if(!Items.Contains(t)) Items.Add(t);
	}

	public void Remove(T t)
	{
		if (Items.Contains(t) Items.Remove(t));
	}
}
```

### Example Use Case
Could be refactored to work on a mini map type project where enemies are stored as a scriptable object list and are removed when either out of range or killed.

```C#
using UnityEngine;

namespace michaelbean.example.codeSet
{
	public class ThingDisabler : Monobehaviour
	{
		public ThingRuntimeSet Set; //Scriptable object reference set in editor

		public void DisableAll()
		{
			for (int i )
		}
	}
}
```