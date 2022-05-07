# Gliese 832 c's Minecraft Technical Metric System #
A standard aiming at making modded Minecraft processing chains, in particularly - but not limited to - tech mods/modpacks far more realistic and consistent. Version 1.0.0.



![gliese_minecrafttechnicalmetricsystem](https://user-images.githubusercontent.com/55159077/167258398-5b4543ff-1e74-47ee-9a91-93b5f6d2cca8.png)
##### **The dark ages of modded Minecraft are about to end. The revolution is coming very soon.** #####



Term definitions:
**Material**: Anything that is somehow used or created in processing. For example: Items, Blocks, Fluids.
**Project**: Mods, modpacks, and anything similar that can use __MTMS__ for its processing chains and the like.



Named after how in the 18th century the metric system aimed to reduce confusion and unify the scattered and inconsistent measurement systems present at the time, __Gliese 832 c's Minecraft Technical Metric System__, also abbreviated as __Gliese's MTMS__ or simply just __MTMS__, is a system/standard designed to unify all kinds of processing chains in modded Minecraft, particulary in, but not limited to, tech projects.

Oftentimes amounts of things like chemicals and metals are all over the place, and it's very hard to design realistic chemical processing chains based off of real values. This system aims to do away with things like different materials of the same type (like liquid) having different amounts. (Such as gems being 666mB and metals 144mb.) Not only will it highly increase the realism and internal consistency of your project, since it's actually grounded in reality through the use of the unit mol, you could - if you wanted to put that much effort into your project - calculate realistic values like the RF/GTEU to Joule convertion ratio, which would further allow you to design even more realistic processes, power storage, fuel values, etc.





#### **1.** Amount based in-game amounts: ####
All amounts are relative to the count of a particles in a material (commonly known as mol). For example, 1000mB of hydrogen gas and 1000mB of oxygen gas represent the same amount of molecules of these two materials. Volume and weight, as well as thermal expansion are ignored for the sake of simplicity as it would turn everything into a mess.





#### **2.** Materials follow the following ratios: ####
**100 Mol __(IRL)__** : **100 Liquid** : **1600 Gas** : **1 Item** : **400 Compressed Gas** : **100 Very Compressed Gas** : **100 Supercritical Fluid** : **50 Supercompressed Supercritical Fluid** : **25 Hypercompressed Supercritical Fluid**
(The last two will rarely be encountered, but are still listed for completeness' sake.)

For example, let's try to represent the following chemical equation: `HCl + H₂O → H₃0⁺•Cl⁻` Hydrogen chloride is a gas, whereas water is a liquid. Using the ratios above, the recipe would look like this in-game: `16mB Hydrogen Chloride + 1mB Water → 1mB Hydrochloric Acid`. Since `H₃0⁺•Cl⁻` is one seen as one single "unit"/molecule, it's represented as 1mB, *not* 2mB.

Since those values are undesirably low for gameplay, you may, of course, use bigger batches of material to represent recipes. `1600mB Hydrogen Chloride + 100mB Water → 100mB Hydrochloric Acid` is a completely valid recipe, representing the reaction of 100 mols of water and 100 mols of hydrogen chloride into 100 mols of hydrochloric acid IRL, that could exist in a machine such as a chemical reactor.

Another example: Let's try representing a more complex chemical equation, like: `Acrolein + Acetaldehyde + Ammonia → Pyridine + 2 Water + Hydrogen`, or `C₃H₄O + C₂H₄O + NH₃ → C₅H₅N + 2H₂O + H₂` Ammonia and hydrogen are gases, the rest are liquids. Translated to __MTMS__, and with a multiplication factor of 100, it would look like this: `100mB Acrolein + 100mB Acetaldehyde + 1600mB Ammonia → 100mB Pyridine + 200mB Water + 1600mB Hydrogen.`

Lastly, let's use some of the less common material types and unconventional materials in an example: `4Fe + 3O₂ → 2Fe₂O₃` Assuming that air is exactly 1/5 oxygen, we could have a recipe like this: `2 Iron Dust + 3000mB Compressed Air → 1 Iron Oxide + 9600mB Deoxygenated Air` This recipe is trickier, as we have to do more math to reach a result. Since the ratio between an item and a compressed gas is 1:400 and we have 2 items, that gives us 800mB. However, you only need 3 oxygen for every iron as seen in the chemical equation above, so dividing that by 4/3 gives us 600mB of compressed oxygen that we would need. In addition to that, since this recipe actually uses compressed air which we assumed to be 1/5 oxygen, we need to multiply the amount of compressed oxygen by a value of 5, giving us 3000mB of compressed air that you need to react with 2 iron to get 1 iron oxide. Since we only actually used the 600mB of oxygen in the air, we would have 2400mB remaining. But if we say that the air decompressed, we have to adjust for that. Since the ratio of compressed gas to gas is 1:4, we simply multiply that number by 4.





#### **3.** Item material splitting: ####
Sometimes you might want to use only tiny amounts of materials. While you can just use low amounts of millibuckets with fluids, that is not possible with items. So the following system has been devised for splitting items:

This:    | Equals to That:
-------- | -----------------------------------------------------
1 Block  | 25 Ingots  = 625 Nuggets = 15625 Flakes = 390625 Specs = 9765625 Tiny Specs
1 Ingot  | 25 Nuggets = 625 Flakes  = 15625 Specs  = 390625 Tiny Specs
1 Nugget | 25 Flakes  = 625 Specs   = 15625 Tiny Specs
1 Flake  | 25 Specs   = 625 Tiny Specs
1 Spec   | 25 Tiny Specs

While most of the time you are not going to go lower than flakes, specs and tiny specs have been added so you can deal with things like realistic gold extraction, where IRL sometimes less than a gram of metal is extracted from a metric ton of ore.

*Note: I am aware that this makes the manual crafting of nuggets into ingots, ingots into blocks, etc. impossible. This is completely intended design as __MTMS__ is aiming to allow strong realism while maintaining high levels of internal consistency, the best results of which are achieved with ratios such as above, and it's not very realistic to just stick chunks of things like metal together to make bigger ones anyways. The intended path of action is for project authors to add recipes to various metal melting and casting machines to turn the smaller units into the bigger ones. If you do not like this system, feel free to create your own "fork" of __MTMS__ to deal with such things. I recommend going with a value that is far better to do math with in a decimal system instead of the default 9. The only good ones that fit into the 3x3 crafting grid are 5 and 4. Alternatively, perhaps add/use a mod that adds a 5x5 crafting table.*





#### **4.** Solutions and other compound mixtures: ####
To avoid a messy system of solubility, solutions are always treated as one part solute and one part solvent.
For example: `1 Sodium Chloride Dust + 100mB Water → 100mB Sodium Chloride Solution`

For other compound mixtures, where the individual parts of the compounds *do not connect on a molecular/atomic level*, it is added instead, as realistically mixing two immisible substances would actually increase the volume of the total output product:
Example: `1 Iron Oxide Dust + 100mB Water → 200mB Iron Oxide Suspension` 





#### **5.** Name standardization: ####

##### Solutions: #####
Solutions follow the format of `x z Solution(y)`, where x is the name of the solute, y is the name of the solvent, and z is the state of matter of the solution. When the solvent is water, `(y)`may be omitted. When the state of matter of the solution is liquid, `z ` may be omitted.
Examples: `Sodium Chloride Solution`     |     `Iodine Solution(Carbon Tetrachloride)`     |     `Germanium Solid Solution(Silicon)`
*Note: In real life, both solid and gaseous solutions are not called that way and instead have different names. This name convention is only supposed to be used when another name for a solid or gaseous solution does not exist. In fact, these cases are so rare that I had trouble finding one for an example, so I used something that's actually usually known as Silicon-Germanium Alloy.*

There is one exception to the above and that is if the solution is an acid. In that case, the name of the acid is used.
Examples: `Propanoic Acid`     |     `Perchloric Acid`     |     `Nitrous Acid`


##### Diluted Solutions: #####
Sometimes you want to use more diluted solutions such as diluted acids for certain processes. In the following table, `x` is the name of the most concentrated solution as described in the preceding paragraph and the value at the left is the solute to solvent ratio:

Ratio | Name
----- | ---------------------
1:1   | x
1:2   | Lightly Diluted x
1:3   | Somewhat Diluted x
1:4   | Diluted x
1:5   | Moderately Diluted x
1:6   | Strongly Diluted x
1:7   | Highly Diluted x
1:8   | Extremely Diluted x

I.e.: `1000mB Sulfuric Acid + 7000mB Water → 8000mB Extremely Diluted Sulfuric Acid`
While it does not have to be called that way directly, if referring to solutions with 1:1 ratios in descriptions and tutorials and such, the word undiluted may be used.

For all other dilution levels, you may use either of the following systems:
###### A - Ratios: ######
`x to y Diluted z`, where `x` and `y` are the ratio of solute to solvent, `z` the name of the most concentrated solution of the solute. If the solvent is water, `z ` may be omitted. For example: Mixing 1000mB of sodium carbonate solution with 12000mB of water yields you `1 to 12 Diluted Sodium Carbonate Solution`.
Another example: 1000mB of Ethene Solution(Dichloromethane) and 9000mB of Dichloromethane turn into: `1 to 9 Diluted Ethene Solution(Dichloromethane)`
While non-integer numbers may be used, it is highly recommended to use integer ratios, and, if possible, normalize to a solute value of 1. (If not possible, try aiming for the lowest integer solute value instead.) Examples: `50 to 100` → `1 to 2`     |     `10 to 15` → `2 to 3`     |     `5 to 7` (cannot be converted to smaller numbers)

###### B - Percentages: ######
If a ratio using low integer numbers cannot be achieved, you may use a percentage in the format of `x% y(z)` instead, where x is the percentage of the solute compared to the solvent, y is the name of the solute, and z is the name of the solvent. `(z)`, similar to the above formats, may be omitted when the solvent is water. Decimal numbers are to be stated to no less than 3 significant figures if 3 or more are present. More are allowed, if not required. Repeating decimals are to be represented by the use of brackets.
Examples: `14% Potassium Carbonate Solution`     |     `37.462% Sodium Nitrate Solution(Ammonia)`     |     `33.[3]% Iodine Solution(Ethanol)`


##### Mixtures: #####
For mixtures of fluids that are not necessarily solutions, use `x y to z w Mixture`, where x is the amount and y the name of the first constituent of the mixture, and z is the amount and w the name of the second constituent of the mixture. This may be extended ad infinitum with more constituents. The constituents must be sorted from highest fraction of total amount to lowest. Examples: `5 Ethanol to 3 Water Mixture`     |     `6 Ammonia to 4 Water to 2 Hydrogen Peroxide to 1 Mineral Oil Mixture`
