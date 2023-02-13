[Link](https://www.youtube.com/watch?v=raQ3iHhE_Kk)

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
			for (int i = Set.Items.Count-1; i >= 0; i --)
			{
				Set.Items[i].gameObject.SetActive(false);
			}
		}
		
		public void DisableRandom()
		{
			int index = Random.Range(0, Set.Items.Count);
			Set.Items[index].gameObject.SetActive(false);
		}
	}
}
```

## Enums
**Shortcomings**
- Have to change in code
- Difficult to remove/reorder
- Can't hold additional data

## Generic Systems
System is ScriptableObject Asset in project
Reference directly with inspector
No code lookup
No scene-only references
Like AudioMixer/AudioMixerGroup

### Inventory
ScriptableObject Master List
ScriptableObject per item
Use different inventories in different scenes

