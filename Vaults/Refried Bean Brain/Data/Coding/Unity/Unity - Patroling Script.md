
```C#
using System.Collections;
using System.Collections.Generic;
using UnityEngine;

public class Patrol : MonoBehaviour
{
	public Transform[] waypoints;
	private int _currentWaypointIndex;
	private float _speed = 2f;

	private void Update()
	{
		Transform wp = waypoints[_currentWaypointIndex];
		if (Vector3.Distance(transform.position, wp.position) < 0.)
	}
}
```