# Code and scripts documentation

> On this page we store information about our features with scripts and codes


### Player Stats
Used scripts:
* Stat (base class with data)
* IBaseStats (mainly health and mana)
* ICombatStats (mainly damage and defense)
* IPlayerStats (mainly attributes)
* PlayerStats : IBaseStats, IPlayerStats, ICombatStats
* PlayerCombatStats : IBaseStats, ICombatStats

> Provides basic data to use in situations such as fight or leveling up  
> Stat class uses ``baseValue``, ``flatIncome``, ``percentIncome`` to calculate true value ([code here](https://github.com/kamreo/birdman/blob/develop/Assets/_SCRIPTS/Player/Stat.cs))  
> It can be reworked in future to better fit items system  

### Inventory system
Used scripts:
* InventoryController (manages picking and placing items in itemGrids)
* InventoryGridItem (item data in inventory)
* GridInteract (manages chosing right itemGrid onPointer interactions)
* ItemGrid (storages data about items in it)
* EquipmentSlot : ItemGrid (special type of grid where can be storage only equipable items)
* WeaponEquipmentSlot : EquipmentSlot (special type with functions to manage types of weapons)
* ItemGroundFrame (item on ground shown as 'label')
* Pickable (pick if in range)
* InventoryHighlighter (item background in inventory)
* InventoryItemDescription (item description in inventory)

> Grid inventory system with equipments slots and available to build other containers such as chests.  
> Every item has size but cannot be rotated.  
> Items on ground are shown as 'name text frames'.  
> Items in inventory have background highlighter and built-up description.  
> Description contains: (always) item name, requierements, base and additional stats.
> Certain type of items can be equipped in suitable slots and provide profits to player.

### Item data
Used scripts:
* ItemStat (storage min and max value for item stat)
* ItemStatSO (storage certain data about stat with tiers system)
* Requierement (storage its name, min, max and calculated value, used mainly for level, dex, int and str)
* ItemData (storage basic item data)
* ItemDataEquipable : ItemData (storage additional equipable data)
* ItemDataUsable : ItemData (storage additional usable data)
* ItemRarityData (storage rarity enum and certain colors)
* EquipmentSlotTypes (enum)
* ItemRariry (enum)

> Provides data to items, mainly requierements, base and additional stats.
> ItemStatSO calculates tier value and rand stat value within min and max range.
> `` Tier = 6 / 80 * itemLevel + Random.Range(0, 2);``
> Tier values are from 0 to 5 (inclusive) and item level from 0 to 80 (inclusive)
