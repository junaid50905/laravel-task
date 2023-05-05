## laravel-task

## CRUD with laravel

#### 1/ create a form
```
@extends('backend.layouts.master')

@section('main_content')
    <form action="{{ route('product.store') }}" method="POST">
      @csrf
        <div class="form-group">
          <label for="" class="form-label">Product Name</label>
          <input type="text" name="product_name" id="" class="form-control" placeholder="" aria-describedby="helpId">
        </div>
        <div class="form-group">
          <label for="" class="form-label">Product Description</label>
          <input type="text" name="product_description" id="" class="form-control" placeholder="" aria-describedby="helpId">
        </div>
        <div class="form-group">
          <label for="" class="form-label">Product Price</label>
          <input type="text" name="product_price" id="" class="form-control" placeholder="" aria-describedby="helpId">
        </div>
        <button class="btn btn-primary mt-2" type="submit">Save</button>
        <button class="btn btn-danger mt-2" type="reset">Cancel</button>
    </form>
@endsection

```
##### action=route('product.store)-------->
##### input name should be same as database table column name


#### 2/ web.php
```
Route::post('/product/store', [ProductController::class, 'store'])->name('product.store');
```

#### 3/ ProductController.php
```
public function store(Request $request)
    {
        $new_product = $request->all();
        Product::create($new_product);
        return redirect()->route('product.list');
    }
```

#### 4/ app/Models/Product.php
```
<?php

namespace App\Models;

use Illuminate\Database\Eloquent\Factories\HasFactory;
use Illuminate\Database\Eloquent\Model;

class Product extends Model
{
    use HasFactory;
    protected $table = 'products';
    protected $fillable = ['product_name', 'product_description', 'product_price'];
}

```



















































