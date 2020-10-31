# Configs
Scriptable Object Configs for data storage

## Usage

Creating Config:

```csharp
	[CreateAssetMenu(menuName = "Game/Configs/Player")]
	public class PlayerConfig : Config
	{
		[SerializeField] private float _startPlayerHealth = 100f;

		public float StartPlayerHealth => _startPlayerHealth;
	}
```

Now you need to create an asset and put it in Resources folder

Get Data from Config:

```csharp
	public class Player : MonoBehaviour
	{
		private float _health = 0f;

		private void Awake()
		{
			_health = Config.Get<PlayerConfig>().StartPlayerHealth;
		}
	}
```
