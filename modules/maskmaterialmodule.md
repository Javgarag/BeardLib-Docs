# Mask Material

Updated for version 3.38.

## Module Definition

The module is inherited from [ItemModuleBase](https://luffyyy.gitbook.io/beardlib/modules/modulebase#itemmodulebase). So base parameters can be found there.

This modules let's you add mask materials.

### Module name

The name of the module you use as the meta of the module definition is 'MaskMaterial' or 'MaskMaterialModule' if `_force_search` is set to true in the module definition.

### XML Structure

```markup
<MaskMaterial id texture global_value material_amount/>
```

#### `<MaskMaterial ...>`

| Parameter | Type | Description |
| :--- | :--- | :--- |
| id | String | The ID of the material |
| texture | String | The path of the material's texture. You'll need to load it through [AddFiles](https://luffyyy.gitbook.io/beardlib/modules/addfilesmodule). Defaults to units/mods/matcaps/`id`\_df |
| global\_value | String | For packs of mods, a global id assigned to all. A nice way to label your mods. You'll still have to create the global value through [GlobalValueModule](https://luffyyy.gitbook.io/beardlib/modules/globalvaluemodule) |
| material\_amount | Integer | How the material is applied to the mask. Set to 0 to have it tile across the mask. Remove it to have it strech over the mask |
| name\_id | String | A localization ID for the pattern \(Defaults to material\_ + `id` + \_title\) |
| texture\_bundle\_folder | String | Optional folder to contain the icon. The path will be guis/dlcs/ `texture_bundle_folder`/textures/pd2/blackmarket/icons/materials/`id`. Defaults to mods with ver="2" |
| ver | Number | Version of the module. 2 makes `texture_bundle_folder` default to mods |

And any other tweakdata value. There are more that are not listed here yet.

#### The icon

The icon will be stored in guis/dlcs/mods/textures/pd2/blackmarket/icons/materials and will be named `id`.texture You will then need to add it using [AddFiles](https://luffyyy.gitbook.io/beardlib/modules/addfilesmodule).

### Example

This example is what you would put inside your main node within your [mod config](https://github.com/GreatBigBushyBeard/PAYDAY-2-BeardLib/wiki/Module-Config)

```markup
<MaskMaterial id="bubblewrap" material_amount="0"/>
```

This will add the mask material `bubblewrap`. You will still need to localize the name of the material. In this case `material_bubblewrap_title` will need to be localized using [LocalizationModule](https://luffyyy.gitbook.io/beardlib/modules/localizationmodule). And add the texture which is currently `units/mods/matcaps/matcap_bubblewrap_df` and icon through [AddFiles](https://luffyyy.gitbook.io/beardlib/modules/addfilesmodule)

#### Template

Download template [here](https://minhaskamal.github.io/DownGit/#/home?url=https://github.com/ModWorkshop/BeardLib-Templates/tree/master/Material-Template)

