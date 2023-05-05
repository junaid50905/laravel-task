## laravel-task

## CRUD with laravel
##### 1/ create a form
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

