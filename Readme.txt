first a list of modified files (which are not part of zip-archive!)
 http://epochmod.com/forum/index.php?/topic/6332-howto-add-chernarus-spawnselection/
- description.ext
- init.sqf
- mission.sqm
 
(dayz_server.pbo)
- compile/server_playerSetup.sqf
 
added folders and files (content of zip-archive)
 
- dayz_code/config/
  - RscDisplaySpawnSelecter.hpp
 
- dayz_code/system/
  - player_monitor.fsm
  - player_monitor.sqf
 
------------------

Credits
-------
TheVisad - Code 
Joe Horan - Picture and design
 
download the attached zip-archive  and extract the file(s) from client-folder into your missionfolder. 
Copy and replace the file(s) from server-folder in your dayz_server.pbo. If you use other folderstructures/filenames, change the given paths.
 

in description.ext add at bottom ...
#include "dayz_code\config\RscDisplaySpawnSelecter.hpp"
 
 
in init.sqf add to listed variables
dayz_spawnselection = 1; // DayZ Spawnselection / 1 = enabled // 0 = disabled, No current spawn limits.
 
in init.sqf delete following line ...
_playerMonitor =     [] execVM "\z\addons\dayz_code\system\player_monitor.sqf";
and replace with that one...
_playerMonitor =     [] execVM "dayz_code\system\player_monitor.sqf";
 
 
in mission.sqm replace class Markers with that ones...
Spoiler 
	class Markers
	{
		items=18;
		class Item0
		{
			position[]={7839.6055,381.33774,8414.7324};
			name="center";
			type="Empty";
		};
		class Item1
		{
			position[]={-7245.377,365.98782,19535.367};
			name="respawn_west";
			type="Empty";
		};
///////////////////////////// spawnselector - begin /////////////////////////////
		class Item2
		{
			position[]={4932,0,1989};
			name="spawn0"; //spawn_balota
			type="Empty";
		};
		class Item3
		{
			position[]={2236,0,1923};
			name="spawn1"; //spawn_kamenka
			type="Empty";
		};
		class Item4
		{
			position[]={8738,0,2122};
			name="spawn2"; //spawn_cherno
			type="Empty";
		};
		class Item5
		{
			position[]={10909,0,2422};
			name="spawn3"; //spawn_elektro
			type="Empty";
		};
		class Item6
		{
			position[]={13510,0,5249};
			name="spawn4"; //spawn_sol
			type="Empty";
		};
		class Item7
		{
			position[]={12048,0,8352};
			name="spawn5"; //spawn_berezino
			type="Empty";
		};
///////////////////////////// spawnselector - end /////////////////////////////
		class Item8
		{
			position[]={6326.4805,304.99265,7809.4888};
			name="Tradercitystary";
			text="Trader City Stary";
			type="mil_circle";
			colorName="ColorBlack";
		};
		class Item9
		{
			position[]={4361.4937,3,2259.9526};
			name="wholesaleSouth";
			text="Wholesaler";
			type="mil_dot";
			colorName="ColorBlack";
		};
		class Item10
		{
			position[]={13532.614,3.0083523,6355.9497};
			name="boatTraderEast";
			text="Wholesaler";
			type="mil_dot";
			colorName="ColorBlack";
		};
		class Item11
		{
			position[]={7989.3354,0.30462033,2900.9946};
			name="BoatDealerSouth";
			text="Boat Dealer";
			type="mil_dot";
			colorName="ColorBlack";
		};
		class Item12
		{
			position[]={12060.471,158.85699,12638.533};
			name="AirVehicles";
			text="Aircraft Dealer";
			type="mil_dot";
			colorName="ColorGreen";
		};
		class Item13
		{
			position[]={1606.6443,289.70795,7803.5156};
			name="BanditDen";
			text="Bandit Camp";
			type="mil_dot";
			colorName="ColorRed";
		};
		class Item14
		{
			position[]={11447.91,317.27109,11364.536};
			name="Klen";
			text="Trader City Klen";
			type="mil_circle";
			colorName="ColorGreen";
		};
		class Item15
		{
			position[]={13441.16,1.1406164,5429.3013};
			name="BoatDealerEast";
			text="Boat Dealer";
			type="mil_dot";
			colorName="ColorBlack";
		};
		class Item16
		{
			position[]={4064.2258,365.13501,11665.938};
			name="TradercityBash";
			text="Trader City Bash";
			type="mil_circle";
			colorName="ColorBlack";
		};
		class Item17
		{
			position[]={12944.227,210.19823,12766.889};
			name="HeroTrader";
			text="Hero Camp";
			type="mil_dot";
			colorName="ColorBlue";
		};
	};
