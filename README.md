# Laravel DKIM
Package, that allows sign emails with DKIM.

# DOES NOT CURRENTLY WORK WITH LARAVEL 7

## Installation
1. Install via Composer:
```
composer require Fossil01/laravel-dkim
```
2. In `config/app.php` comment line with original service provider:
```
// Illuminate\Mail\MailServiceProvider::class,
```
3. In `config/app.php` add following line to provider's section:
```
Vitalybaev\LaravelDkim\DkimMailServiceProvider::class,
```
4. Fill your settings in `config/mail.php`:
```
'dkim_selector' => env('MAIL_DKIM_SELECTOR'), // selector, required
'dkim_domain' => env('MAIL_DKIM_DOMAIN'), // domain, required
'dkim_private_key' => env('MAIL_DKIM_PRIVATE_KEY'), // path to private key, required
'dkim_identity' => env('MAIL_DKIM_IDENTITY'), // identity (optional)
'dkim_algo' => env('MAIL_DKIM_ALGO'), // sign algorithm (defaults to rsa-sha256)
'dkim_passphrase' => env('MAIL_DKIM_PASSPHRASE'), // private key passphrase (optional)
``z
