
```C#
namespace ALS_BehaviorTree
{
	public enum NodeState
	{
	
	}
	
	public class Node
	{
		public bool ClearData(string key)
		{
			if (_dataContext.ContainsKey(key))
			{
			_dataContext.Remove(key);
			return true;
			}
			
			Node node = parent;
			
			while (node != null)
			{
				bool cleared = node.ClearData(key);
				if (cleared)
				return true;
				node = node.parent;
			}
			return false;
		}
	}
}
```