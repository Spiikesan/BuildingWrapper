**Building Wrapper** is meant to simplify setting up [Zone Manager](/plugins/zone-manager) zones around buildings.  This plugin will allow a player to look at a building, execute a command, and have a zone automatically created, moved, scaled, and rotated to fit that building.  
  
## Permissions
Requires the ZoneManager permission (_zonemanager.zone_) or auth level > 0 to use.
  
## Commands  
- `/bw wrap <zone_id> <shape> <buffer>` -- Wrap the building which is being looked at in a zone.  If the `<zone_id>` is the ID of an existing zone, the zone will be moved, scaled, and rotated if necessary to fit the building being looked at.  **Preview:** Passing "_preview_" as `<zone_id>` will draw a preview of the zone dimensions, as well as the building perimeter being used.  
- `/bw rewrap <zone_id> <shape> <buffer>` -- Rewraps structures in the specified zone to fit entirely inside the zone. `<zone_id>` must be the name of an existing zone.  
- `/bw extend <zone_id> <shape> <buffer>` -- Extend an existing zone to include the specified structure.  `<zone_id>` must be the name of an existing zone.  
  
The `<zone_id>` parameter is required, but entering "auto" will enable an ID to be auto-generated.  
Optional parameters include _shape _(either "box" or "sphere" - "sphere" is default if not entered), and _buffer_ size (defaults to _1_), which is the distance the zone should extend beyond the building.  
  
Setting `<buffer>` to a positive value increases the size of the zone, while setting a negative value will reduce the size of the zone.  
  
**Shapes:**  
- `box` -- Wraps the building in a box zone - the zone size and rotation is the smallest surrounding rectangle that can fit around the building perimeter.  
- `square` -- Similar to _box_ but with equal length/width.  (Rotation may not be the same as _box_ rotation on the same building)  
- `sphere` -- Wraps the building in the smallest possible spherical zone which encompasses the entire building.

## TODO
 - Code refactoring. May take some time.