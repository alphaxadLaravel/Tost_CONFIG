# Laravel Toast Notifications

Configure Toast Notifications Here

## Require Package
```
composer require realrashid/sweet-alert

```
## Setup In Layout
```
<!DOCTYPE html>
<html>
<head>
    <title>Your Application</title>
    <link href="https://cdn.jsdelivr.net/npm/sweetalert2@11/dist/sweetalert2.min.css" rel="stylesheet">
</head>
<body>
    <!-- Your content here -->

    <script src="https://cdn.jsdelivr.net/npm/sweetalert2@11"></script>
    @include('sweetalert::alert')
</body>
</html>

```
## Call In Controllers
```
<?php

namespace App\Http\Controllers;

use RealRashid\SweetAlert\Facades\Alert;

class ExampleController extends Controller
{
    public function showSuccess()
    {
        Alert::success('Success', 'Operation successful!')
            ->icon('success')
            ->position('top-end')
            ->timer(3000)
            ->showConfirmButton(true)
            ->confirmButtonText('OK')
            ->confirmButtonColor('#3085d6'); // Set your desired color here
        return redirect()->route('your.route.name');
    }

    public function showError()
    {
        Alert::error('Error', 'Operation failed!')
            ->icon('error')
            ->position('top-end')
            ->timer(3000)
            ->showConfirmButton(true)
            ->confirmButtonText('OK')
            ->confirmButtonColor('#d33'); // Set your desired color here
        return redirect()->route('your.route.name');
    }

    public function showWarning()
    {
        Alert::warning('Warning', 'This is a warning!')
            ->icon('warning')
            ->position('top-end')
            ->timer(3000)
            ->showConfirmButton(true)
            ->confirmButtonText('OK')
            ->confirmButtonColor('#f0ad4e'); // Set your desired color here
        return redirect()->route('your.route.name');
    }

    public function showInfo()
    {
        Alert::info('Info', 'This is some information.')
            ->icon('info')
            ->position('top-end')
            ->timer(3000)
            ->showConfirmButton(true)
            ->confirmButtonText('OK')
            ->confirmButtonColor('#17a2b8'); // Set your desired color here
        return redirect()->route('your.route.name');
    }
}

```
## Customized Small
```
use RealRashid\SweetAlert\Facades\Alert;

Alert::toast('This is a toast message!', 'success', [
    'position' => 'top-end',
    'timer' => 3000,
    'showConfirmButton' => true,
    'confirmButtonText' => 'Got it!',
    'confirmButtonColor' => '#3085d6' // Custom color
]);
```