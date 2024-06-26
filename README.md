![Filament Minimalist Theme Banner](art/banner.jpg)
# Filament Minimalist Theme
The Filament Minimalist Theme is a modern and minimalistic theme for your Filament panel.
Minimalist is also responsive on any device and supports dark-mode.

## Screenshots
### Light Theme
![List customers page in light mode](art/light_customers.png)
![Edit product in light mode](art/light_edit_product.png)
![Show notifications in light mode](art/light_notifications.png)
![Login page in light mode](art/light_login.png)


### Dark Theme
![Login page in dark mode](art/dark_login.png)
![Dashboard page in dark mode](art/dark_dashboard.png)
![List customers page in dark mode](art/dark_customers.png)
![Edit product in dark mode](art/dark_edit_product.png)



## Installation

Filament Minimalist Theme can be installed using our private Composer repository. Configure the repository in your
application's composer.json file:

```json
"repositories": [
  {
    "type": "composer",
    "url": "https://filament-minimalistic-theme.composer.sh"
  }
]
```

Now you can install the package using:
```bash
composer require angelej/filament-minimalist-theme:^3.0
```
You will be prompted to provide a username and password. Use your license email address as username and the license key you received as password.

## Setup


To start using the Theme with the Filament Panel Builder, you need to [create a custom theme](https://filamentphp.com/docs/3.x/panels/themes#creating-a-custom-theme).

Next, replace the imported Panel Builder stylesheet with the Minimalist Theme stylesheet in your theme CSS file:

```diff
- @import '/vendor/filament/filament/resources/css/theme.css';
+ @import '/vendor/angelej/filament-minimalist-theme/resources/css/index.css';
```
Now compile your theme stylesheet using `npm run build`.

Finally, register the theme plugin in your panel configuration file:
```php
<?php
 
namespace App\Providers\Filament;
 
use Angelej\FilamentMinimalistTheme\FilamentMinimalistTheme;
use Filament\Panel;
use Filament\PanelProvider;
 
class AdminPanelProvider extends PanelProvider
{
    public function panel(Panel $panel): Panel
    {
        return $panel
            ->plugin(FilamentMinimalistTheme::make())
            ->viteTheme('resources/css/filament/admin/theme.css');
    }
}
```
