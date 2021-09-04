# roblox-probe-2

## Zombie
```
local spawner = require(workspace.Spawner);

RADIUS = 150;

while(true) do
	wait(3);
	local x = math.random()*RADIUS - RADIUS/2;
	local z = math.random()*RADIUS - RADIUS/2;
	new_zombie = spawner.Spawn(x, z, workspace.Prefabs.Zombie);
	new_zombie.NPC.Disabled = false;
end

```


## Spavner
```
local module = {}

function module.Spawn(x, z, source)
	if not source then
		return;
	end
	local cloned = source:Clone();
	cloned.Parent = workspace;

	local center = source.PrimaryPart.CFrame.Position;
	local new_pos = Vector3.new(x, center.Y, z);
	cloned:MoveTo(new_pos);

	return cloned;
end

return module
```
