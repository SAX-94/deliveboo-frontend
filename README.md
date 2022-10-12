# deliveboo

composer create-project --prefer-dist laravel/laravel:^7.0 deliveboo

npm install

composer require laravel/ui:^2.4

php artisan ui vue --auth

php artisan migrate

php artisan make:model -m NomeAlSingolare

php artisan migrate:rollback

php artisan make:seeder UsersTableSeeder / DishesTableSeeder / CategoriesTableSeeder

php artisan db:seed --class UsersTableSeeder

php artisan make:controller --resource UserController //CRUD

composer dump-autoload

php artisan make:migration create_dish_order_table

php artisan make:migration add_foreign_keys_to_orders_table


    public function user()
    {
        return $this->belongsTo('App\User');
    }

    public function orders()
    {
        return $this->belongsToMany('App\Model\Order');
    }

    public function getRouteKeyName()
    {
        return 'slug';
    }

    public function createSlug($name)
    {
        $slug = Str::slug($name, '-');

        $oldDish = Dish::where('slug', $slug)->first();

        $counter = 0;
        while ($oldDish) {
            $newSlug = $slug . '-' . $counter;
            $oldDish = Dish::where('slug', $newSlug)->first();
            $counter++;
        }

        return (empty($newSlug)) ? $slug : $newSlug;
    }
}

*********************************
    VALIDAZIONE FILE DIMENSIONI KILOBYTES:
*********************************
https://laravel.com/docs/7.x/validation#rule-size


*********************************
    FILE UPDATE (IMMAGINI)
*********************************
use Illuminate\Support\Facades\Storage;


*********************************
        META Auth
{
    path: 'bar',
    component: Bar,
    // a meta field
    meta: { requiresAuth: true }
}
*********************************


***************************************
    FINESTRE POPUP PERSONALIZZABILI CON TASTI
***************************************
https://sweetalert2.github.io/