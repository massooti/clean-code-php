<h1 dir="rtl">Clean Code PHP</h1>

<h2  dir="rtl"><a id="table-of-contents" class="anchor" href="#table-of-contents"></a>فهرست مندرجات</h2>

<ol dir="rtl">
<li><a href="#introduction">مقدمه</a></li>
<li><a href="#variables">متغیر ها</a><ul>
<li><a href="#use-meaningful-and-pronounceable-variable-names">استفاده از نام های معنی دار و قابل تلفظ برای نام گذاری متغیر ها</a></li>
<li><a href="#use-the-same-vocabulary-for-the-same-type-of-variable">استفاده از واژگان مشابه برای همان نوع متغیر</a></li>
<li><a href="#use-searchable-names-part-1"> استفاده از واژگان قابل جستجو (قسمت اول)</a></li>
<li><a href="#use-searchable-names-part-2"> استفاده از واژگان قابل جستجو (قسمت دوم)</a></li>
<li><a href="#use-explanatory-variables">استفاده از متفیر های توضیح دهنده</a></li>
<li><a href="#avoid-nesting-too-deeply-and-return-early-part-1">اجتناب از ایجاد کدهای تودرتو و بازگشت(قسمت اول)</a></li>
<li><a href="#avoid-nesting-too-deeply-and-return-early-part-2">اجتناب از ایجاد کدهای تودرتو و بازگشت(قسمت دوم)</a></li>
<li><a href="#avoid-mental-mapping">اجتناب از نقشه ذهنی</a></li>
<li><a href="#don-t-add-unneeded-context">محتوا غیر ضروری را اضافه نکنید</a></li>
<li><a href="#use-default-arguments-instead-of-short-circuiting-or-conditionals">استفاده از آرگومان های پیش فرض به جای شرط ها یا short circuiting</a></li>
</ul>
</li>
<li><a href="#comparison">مقایسه</a><ul>
<li><a href="#use-identical-comparison">استفاده از identical comparison </a></li>
</ul>
</li>
<li><a href="#functions">توابع</a><ul>
<li><a href="#function-arguments-2-or-fewer-ideally">آرگومان های توابع ( ۲ تا یا در حالت ایده آل کمتر)</a></li>
<li><a href="#functions-should-do-one-thing">توابع باید یک چیز را انجام بدهند</a></li>
<li><a href="#function-names-should-say-what-they-do">نام توابع باید بگوید چه کاری انجام می دهد</a></li>
<li><a href="#functions-should-only-be-one-level-of-abstraction">توابع باید تنها یک سطح انتزاع داشته باشند</a></li>
<li><a href="#dont-use-flags-as-function-parameters">از flags  پارمترهای در توابع استفاده نکنید</a></li>
<li><a href="#avoid-side-effects">اجتناب از اثرات جانبی</a></li>
<li><a href="#dont-write-to-global-functions">توابع عمومی ننویسید</a></li>
<li><a href="#dont-use-a-singleton-pattern">از دیزاین پترن سینگلتون استفاده نکنید</a></li>
<li><a href="#encapsulate-conditionals">کپسوله کردن شرط ها</a></li>
<li><a href="#avoid-negative-conditionals">اجتناب از شرط های منفی</a></li>
<li><a href="#avoid-conditionals">اجتناب از شرط ها</a></li>
<li><a href="#avoid-type-checking-part-1">اجتناب از type-checking (قسمت اول)</a></li>
<li><a href="#avoid-type-checking-part-2">اجتناب از type-checking (قسمت دوم)</a></li>
<li><a href="#remove-dead-code">کدهای مرد را پاک کنید</a></li>
</ul>
</li>
<li><a href="#objects-and-data-structures">اشیا و ساختارهای داده </a><ul>
<li><a href="#use-object-encapsulation">استفاده از کپسوله سازی اشیا</a></li>
<li><a href="#make-objects-have-privateprotected-members">اشیایی بسازید که اعضای private/protected داشته باشند</a></li>
</ul>
</li>
<li><a href="#classes">کلاس ها</a><ul>
<li><a href="#prefer-composition-over-inheritance">ترکیب را به ارث بری ترجیح بدهید</a></li>
<li><a href="#avoid-fluent-interfaces">اجتناب از fluent interfaces </a></li>
<li><a href="#prefer-final-classes">ترجیح تان کلاس های <code>final</code>  باشند</a></li>
</ul>
</li>
<li><a href="#solid">SOLID</a><ul>
<li><a href="#single-responsibility-principle-srp"> اصل Single Responsibility (SRP)</a></li>
<li><a href="#openclosed-principle-ocp">Open/Closed اصل (OCP)</a></li>
<li><a href="#liskov-substitution-principle-lsp">Liskov Substitution اصل (LSP)</a></li>
<li><a href="#interface-segregation-principle-isp">Interface Segregation اصل (ISP)</a></li>
<li><a href="#dependency-inversion-principle-dip">Dependency Inversion اصل (DIP)</a></li>
</ul>
</li>
<li><a href="#dont-repeat-yourself-dry">خودت را تکرار نکن!</a></li>
<li><a href="#translations">ترجمه ها</a></li>
</ol>
 

<h3 id="variables" dir="rtl"><a class="anchor" name="variables" href="#variables"><span class="octicon octicon-link"></span></a>
<a class="anchor" name="variables" href="#variables">
<span class="octicon octicon-link"></span></a>
مقدمه</h3>

<p dir="rtl">اصول مهندسی نرم افزار، از کتاب <a href="https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882"><em>Clean Code</em></a>,
 نوشته C. Martin، برای PHP سازگار شده است.این یک راهنما ساده نیست.این یک  راهنما برای تولید نرم افزار های با قابلیت خوانایی،استفاده مجدد، و قابل باز سازی در php  می باشد</p>


<p dir="rtl">
هیچ اصل و اصولی در اینجا الزامی نیست و به صورت عمومی توافقی نشده است.اینها یکسری دستور العمل هست نه بیشتر اما تمام آن بر اساس  تجربه چندین ساله جمعی از برنامه نویسان توسط نویسندگان کتاب
  <em>clean code</em>
  نوشته شده است. 
</p>

<p dir="rtl">
الهام گرفته از  <a href="https://github.com/ryanmcdermott/clean-code-javascript">clean-code-javascript</a>
</p>
<p dir="rtl">اگر چه بسیار از توسعه دهندگان هنوز از php ۵ استفاده می کنند ولی بیشتر مثال های ما در php 7.1 به بالا کار میکند.</p>

<h3 id="introduction" dir="rtl"><a class="anchor" name="introduction" href="#introduction"><span class="octicon octicon-link"></span></a>
<a class="anchor" name="introduction" href="#introduction">
<span class="octicon octicon-link"></span></a>
متغیر ها</h3>

<h3 id="use-meaningful-and-pronounceable-variable-names" dir="rtl">
<a class="anchor" name="use-meaningful-and-pronounceable-variable-names" href="#use-meaningful-and-pronounceable-variable-names">
<span class="octicon octicon-link"></span></a>
استفاده از نام های معنی دار و قابل تلفظ برای نام گذاری متغیر ها</h3>
<p  dir="rtl"><strong>بد:</strong></p>

```php
$ymdstr = $moment->format('y-m-d');
```

<p  dir="rtl"><strong>خوب:</strong></p>


```php
$currentDate = $moment->format('y-m-d');
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="use-the-same-vocabulary-for-the-same-type-of-variable" dir="rtl">
<a class="anchor" name="use-the-same-vocabulary-for-the-same-type-of-variable" href="#use-the-same-vocabulary-for-the-same-type-of-variable">
<span class="octicon octicon-link"></span></a>استفاده از واژگان مشابه برای همان نوع متغیر</h3>

<p  dir="rtl"><strong>بد:</strong></p>

```php
getUserInfo();
getUserData();
getUserRecord();
getUserProfile();
```

<p  dir="rtl"><strong>خوب:</strong></p>

```php
getUser();
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 dir="rtl" id="use-searchable-names-part-1">
<a class="anchor" name="use-searchable-names-part-1" href="#use-searchable-names-part-1">
<span class="octicon octicon-link"></span></a>استفاده از واژگان قابل جستجو (قسمت اول)</h3>

<p die="rtl">
ما بیشتر از آن که کد بنویسیم، کدها را میخوانیم.خیلی مهم  می باشد کد هایی که ما مینویسیم  با خوانایی بالا و قابل جستجو باشند. ما با انتخاب نام های نامفهوم و غیرقابل فهم در برنامه های مان به خوانایی کد آسیب میزنم.نام ها را  قابل جستجو انتخاب کنید.
</p>

<p  dir="rtl"><strong>بد:</strong></p>

```php
//عدد  ۴۴۸ برای چی هست ?
$result = $serializer->serialize($data, 448);
```

<p  dir="rtl"><strong>خوب:</strong></p>

```php
$json = $serializer->serialize($data, JSON_UNESCAPED_SLASHES | JSON_PRETTY_PRINT | JSON_UNESCAPED_UNICODE);
```

<h3 dir="rtl" id="use-searchable-names-part-2">
<a class="anchor" name="use-searchable-names-part-2" href="#use-searchable-names-part-2">
<span class="octicon octicon-link"></span></a>استفاده از واژگان قابل جستجو (قسمت دوم)</h3>

<p  dir="rtl"><strong>بد:</strong></p>

```php
// عدد ۴ برای چی هست?
if ($user->access & 4) {
    // ...
}
```

<p  dir="rtl"><strong>خوب:</strong></p>

```php
class User
{
    const ACCESS_READ = 1;
    const ACCESS_CREATE = 2;
    const ACCESS_UPDATE = 4;
    const ACCESS_DELETE = 8;
}

if ($user->access & User::ACCESS_UPDATE) {
    // do edit ...
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="use-explanatory-variables" dir="rtl">
<a class="anchor" name="use-explanatory-variables" href="#use-explanatory-variables">
<span class="octicon octicon-link"></span></a>استفاده از متفیر های توضیح دهنده</h3>

<p  dir="rtl"><strong>بد:</strong></p>


```php
$address = 'bozorgmeher st , valiasr st,tehran';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches[1], $matches[2]);
```

<p dir="rtl">
   <strong>بدک نیست:</strong>
</p>

<p dir="rtl">این بهتر شد ولی ما هنوز وابستگی شدیدی به regex  داریم.</p>

```php
$address = 'bozorgmeher st , valiasr st,tehran';
$cityZipCodeRegex = '/^[^,]+,\s*(.+?)\s*(\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

[, $city, $zipCode] = $matches;
saveCityZipCode($city, $zipCode);
```

<p dir="rtl"><strong>خوب:</strong></p>

<p dir="rtl">با نامگذاری subpattern ها وابستگی به regex را کاهش دادیم.</p>

```php
$address = 'bozorgmeher st , valiasr st,tehran';
$cityZipCodeRegex = '/^[^,]+,\s*(?<city>.+?)\s*(?<zipCode>\d{5})$/';
preg_match($cityZipCodeRegex, $address, $matches);

saveCityZipCode($matches['city'], $matches['zipCode']);
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-nesting-too-deeply-and-return-early-part-1"  dir="rtl">
<a class="anchor" name="avoid-nesting-too-deeply-and-return-early-part-1" href="#avoid-nesting-too-deeply-and-return-early-part-1">
<span class="octicon octicon-link"></span></a>اجتناب از ایجاد کدهای تودرتو و بازگشت(قسمت اول)
</h3>
<p dir="rtl"> استفاده از if و else  های زیاد باعث کاهش خوانایی و پیچیدگی کد میشود.خوانایی و سادگی بهتر از پیچیدگی و گیج کنندگی است</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
function isShopOpen($day): bool
{
    if ($day) {
        if (is_string($day)) {
            $day = strtolower($day);
            if ($day === 'friday') {
                return true;
            } elseif ($day === 'saturday') {
                return true;
            } elseif ($day === 'sunday') {
                return true;
            } else {
                return false;
            }
        } else {
            return false;
        }
    } else {
        return false;
    }
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
function isShopOpen(string $day): bool
{
    if (empty($day)) {
        return false;
    }

    $openingDays = [
        'friday', 'saturday', 'sunday'
    ];

    return in_array(strtolower($day), $openingDays, true);
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>


<h3 id="avoid-nesting-too-deeply-and-return-early-part-2"  dir="rtl">
<a class="anchor" name="avoid-nesting-too-deeply-and-return-early-part-2" href="#avoid-nesting-too-deeply-and-return-early-part-2">
<span class="octicon octicon-link"></span></a>اجتناب از ایجاد کدهای تودرتو و بازگشت(قسمت دوم)
</h3>

<p dir="rtl"><strong>بد:</strong></p>

```php
function fibonacci(int $n)
{
    if ($n < 50) {
        if ($n !== 0) {
            if ($n !== 1) {
                return fibonacci($n - 1) + fibonacci($n - 2);
            } else {
                return 1;
            }
        } else {
            return 0;
        }
    } else {
        return 'Not supported';
    }
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
function fibonacci(int $n): int
{
    if ($n === 0 || $n === 1) {
        return $n;
    }

    if ($n > 50) {
        throw new \Exception('Not supported');
    }

    return fibonacci($n - 1) + fibonacci($n - 2);
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-mental-mapping"  dir="rtl">
<a class="anchor" name="avoid-mental-mapping" href="#avoid-mental-mapping">
<span class="octicon octicon-link"></span></a>اجتناب از نقشه ذهنی</h3>
<p dir="rtl">کاری نکنید کسی که کد شما را میخواند بیشتر زمانش صرف این شود که معنی این متغیر چیست؟خوانایی و سادگی بهتر از پیچیدگی و گیج کنندگی است.
</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
$l = ['Austin', 'New York', 'San Francisco'];

for ($i = 0; $i < count($l); $i++) {
    $li = $l[$i];
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    // Wait, what is `$li` for again?
    dispatch($li);
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
$locations = ['Austin', 'New York', 'San Francisco'];

foreach ($locations as $location) {
    doStuff();
    doSomeOtherStuff();
    // ...
    // ...
    // ...
    dispatch($location);
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="don-t-add-unneeded-context" dir="rtl" >
<a class="anchor" name="don-t-add-unneeded-context" href="#don-t-add-unneeded-context">
<span class="octicon octicon-link"></span></a>محتوا غیر ضروری را اضافه نکنید</h3>


<p dir="rtl">اگر نام کلاس یا شی شما اطلاعاتی به شما میدهد لطفا آن را در نام متغیر ها تکرار نکنید.</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
class Car
{
    public $carMake;
    public $carModel;
    public $carColor;

    //...
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
class Car
{
    public $make;
    public $model;
    public $color;

    //...
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="use-default-arguments-instead-of-short-circuiting-or-conditionals" dir="rtl">
<a class="anchor" name="use-default-arguments-instead-of-short-circuiting-or-conditionals" href="#use-default-arguments-instead-of-short-circuiting-or-conditionals">
<span class="octicon octicon-link"></span></a>استفاده از آرگومان های پیش فرض به جای short circuit یا شرط ها</h3>    
<p dir="rtl"><strong>خوب نیست:</strong></p>
    <p dir="rtl">این خوب نیست چون <code dir="ltr">$breweryName</code> میتواند <code>NULL</code>  باشد.</p>

```php
function createMicrobrewery($breweryName = 'بهنوش'): void
{
    // ...
}
```

<p dir="rtl"><strong>بدک نیست:</strong></p>
<p dir="rtl">این کد قابل فهم تر از کد قبلی هست، اما بهتر است کنترل بهتری بر مقدار متغیر ها داشته باشد.</p>

```php
function createMicrobrewery($name = null): void
{
    $breweryName = $name ?: 'بهنوش';
    // ...
}
```

<p dir="rtl"><strong>خوب:</strong></p>

<p dir="rtl"> شما میتوانید از  <a href="http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration">type hinting</a> استفاده کنید  و مطمئن شوید که  <code dir="ltr">$breweryName</code> هیچ موقع <code>NULL</code> نخواهد بود</p>

```php
function createMicrobrewery(string $breweryName = 'بهنوش'): void
{
    // ...
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h2 id="comparison" dir="rtl"><a class="anchor" name="comparison" href="#comparison"><span class="octicon octicon-link"></span></a>مقایسه</h2>

<h3 id="use-identical-comparison" dir="rtl">
<a class="anchor" name="use-identical-comparison" href="#use-identical-comparison">
<span class="octicon octicon-link"></span></a>استفاده از <a href="http://php.net/manual/en/language.operators.comparison.php">identical comparison</a> </h3>

<p dir="rtl"><strong>خوب نیست:</strong></p>

<p dir="rtl">یک مقایسه ساده که یک رشته را به عدد صحیح تبدیل میکند.</p>


```php
$a = '42';
$b = 42;

if ($a != $b) {
   // هر کدی اینجا باشد  اجرا تخواهد شد.
}
```


<p dir="rtl">مقایسه <code dir="ltr">$a != $b</code> به ما <code dir="ltr">FALSE</code> بر میگرداند اما در حقیقت باید <code dir="ltr">TRUE</code> برگرداند.چون رشته <code dir="ltr">42</code> تفاوت دارد با عدد صحیح <code dir="ltr">42</code></p>

<p dir="rtl"><strong>خوب :</strong></p>
<p dir="rtl"><strong>identical comparison</strong> نوع و مقدار را مقایسه میکند.</p>

```php
$a = '42';
$b = 42;

if ($a !== $b) {
    // هر کدی اینجا باشد اجرا میشود.
}
```

<p dir="rtl">مقایسه <code dir="ltr">$a !== $b</code> به ما  <code>TRUE</code> بر میگرداند.</p>
<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>


## توابع

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-mental-mapping"  dir="rtl">
<a class="anchor" name="avoid-mental-mapping" href="#avoid-mental-mapping">
### <span class="octicon octicon-link"></span></a>آرگومانهای تابع  (در حالت ایده آل ۲ پارامتر یا کمتر)</h3>
<p dir="rtl">
محدود کردن مقدار پارامترهای عملکرد بسیار مهم است زیرا 
عملکرد تابع شما را آسان تر می کند. داشتن بیش از ۳ تا پارامتر در ورودی های تابع مورد نظر منجر به انفجار ترکیبی می شود
که در آن شما باید تعداد موارد مختلف را با هر استدلال جداگانه آزمایش کنید. 

بطور کلی ایجاد تابع بدون پارامتر ورودی بسیار ایده آل است. یک یا دو پارامتر هم خوب است و اما استفاده از سه پارامتر بیشتر در ورودی تابع باید تا حد امکان جلوگیری شود. باید از سه بحث جلوگیری شود
هر چیزی بیش از این باید ادغام شود. معمولاً اگر بیش از دو نفر دارید
آرگومان ها سپس عملکرد شما تلاش می کند کارهای زیادی انجام دهد. در مواردی که اینگونه نباشد ، بیشتر
از آن زمان یک شی-سطح بالاتر به عنوان یک استدلال کافی است. 
</p>

<p dir="rtl"><strong>بد:</strong></p>


```php
function createMenu(string $title, string $body, string $buttonText, bool $cancellable): void
{
    // ...
}
```
<p dir="rtl"><strong>خوب:</strong></p>

```php
class MenuConfig
{
    public $title;
    public $body;
    public $buttonText;
    public $cancellable = false;
}

$config = new MenuConfig();
$config->title = 'Foo';
$config->body = 'Bar';
$config->buttonText = 'Baz';
$config->cancellable = true;

function createMenu(MenuConfig $config): void
{
    // ...
}
```


<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-mental-mapping"  dir="rtl">
<a class="anchor" name="avoid-mental-mapping" href="#function-names-should-say-what-they-do">
<span class="octicon octicon-link"></span></a>توابع باید فقط یک کار انجام دهند</h3>
<p dir="rtl">
این مهمترین قانون در مهندسی نرم افزار است. وقتی یک تابع بیش از یک کار را انجام می دهد
 متعاقبا نوشتن ، تست  و استدلال و کمپایل آن دشوار تر است. و وقتی شما یک تابع را ایزوله و محدود به انجام یک کار میکنید 
 در آینده آن تابع  می تواند به راحتی بازسازی شود و کد شما بسیار روان تر ، تمیز تر و خواناتر خواهد شد
اهیمن این نکته بقدری بالاست که اگر از کل این داکیومنت فقط همین یک نکته را استفاده کنید ، دو هیچ از بقیه برنامه نویسا جلوترید.
.
</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
function emailClients(array $clients): void
{
    foreach ($clients as $client) {
        $clientRecord = $db->find($client);
        if ($clientRecord->isActive()) {
            email($client);
        }
    }
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
function emailClients(array $clients): void
{
    $activeClients = activeClients($clients);
    array_walk($activeClients, 'email');
}

function activeClients(array $clients): array
{
    return array_filter($clients, 'isClientActive');
}

function isClientActive(int $client): bool
{
    $clientRecord = $db->find($client);

    return $clientRecord->isActive();
}
```

**[⬆ back to top](#table-of-contents)**

### 

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-mental-mapping"  dir="rtl">
<a class="anchor" name="avoid-mental-mapping" href="#function-names-should-say-what-they-do">
<span class="octicon octicon-link"></span></a>اسم تابع باید گویای کاری که قراره انجام بده باشه</h3>


<p dir="rtl"><strong>بد:</strong></p>


```php
class Email
{
    //...

    public function handle(): void
    {
        mail($this->to, $this->subject, $this->body);
    }
}

$message = new Email(...);
/* خب این الان چه اسمیه ؟! 
این الان یه تابع برای هندل کردن یه پیامه یا چی ؟! 
نکنه ما الان داریم یک نامه مینویسیم اصلا؟!!!
*/
$message->handle();
```

**خوب:**

```php
class Email 
{
    //...

    public function send(): void
    {
        mail($this->to, $this->subject, $this->body);
    }
}

$message = new Email(...);
//شفاف و واضح
$message->send();
```
<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-mental-mapping"  dir="rtl">
<a class="anchor" name="avoid-mental-mapping" href="#functions-should-only-be-one-level-of-abstraction">
<span class="octicon octicon-link"></span></a>توابع باید فقط یک سطح انتزاعی داشته باشند</h3>
<p dir="rtl">
اوقتی  توی تابع بیش از یک سطح انتزاع داشته باشید ، عملیات توی تابع  شما معمولاً بیش از حد انجام می شود
اینه که تقسییم محتوای یک تابع بزرگ به چندتا تابع کوچیک ، عملکرد و بهینگی کد شمارو بالاتر میبره
.
</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
function parseBetterJSAlternative(string $code): void
{
    $regexes = [
        // ...
    ];

    $statements = explode(' ', $code);
    $tokens = [];
    foreach ($regexes as $regex) {
        foreach ($statements as $statement) {
            // ...
        }
    }

    $ast = [];
    foreach ($tokens as $token) {
        // lex...
    }

    foreach ($ast as $node) {
        // parse...
    }
}
```
<p dir="rtl"><strong>اینم باز داغونه:</strong></p>

<p dir="rtl">
 `parseBetterJSAlternative()`تو این قسمت ما بعضی از کدهارو از تابع جدا کردیم ،اما همچنان  این تابع 
 خیلی پیچیدس و به راحتی نمیشه اونو تست و استفاده کرد
.
</p>

```php
function tokenize(string $code): array
{
    $regexes = [
        // ...
    ];

    $statements = explode(' ', $code);
    $tokens = [];
    foreach ($regexes as $regex) {
        foreach ($statements as $statement) {
            $tokens[] = /* ... */;
        }
    }

    return $tokens;
}

function lexer(array $tokens): array
{
    $ast = [];
    foreach ($tokens as $token) {
        $ast[] = /* ... */;
    }

    return $ast;
}

function parseBetterJSAlternative(string $code): void
{
    $tokens = tokenize($code);
    $ast = lexer($tokens);
    foreach ($ast as $node) {
        // parse...
    }
}
```

<p dir="rtl"><strong>خوب:</strong></p>
<p dir="rtl">
بهترین راه برای هندل کردن همیچین توابعی اینه که تمام متعلقات و وابستگی های تابع رو ازش بیاری بیرون
جدا کنی و هرجا که نیازه به متد پاس بدی ، دقیقا اینجاست که مفهوم dependency injection بکار میاد
.
</p>

```php
class Tokenizer
{
    public function tokenize(string $code): array
    {
        $regexes = [
            // ...
        ];

        $statements = explode(' ', $code);
        $tokens = [];
        foreach ($regexes as $regex) {
            foreach ($statements as $statement) {
                $tokens[] = /* ... */;
            }
        }

        return $tokens;
    }
}

class Lexer
{
    public function lexify(array $tokens): array
    {
        $ast = [];
        foreach ($tokens as $token) {
            $ast[] = /* ... */;
        }

        return $ast;
    }
}

class BetterJSAlternative
{
    private $tokenizer;
    private $lexer;

    public function __construct(Tokenizer $tokenizer, Lexer $lexer)
    {
        $this->tokenizer = $tokenizer;
        $this->lexer = $lexer;
    }

    public function parse(string $code): void
    {
        $tokens = $this->tokenizer->tokenize($code);
        $ast = $this->lexer->lexify($tokens);
        foreach ($ast as $node) {
            // parse...
        }
    }
}
```

**[⬆ back to top](#table-of-contents)**

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="dont-use-flags-as-function-parameters"  dir="rtl">
<a class="anchor" name="dont-use-flags-as-function-parameters" href="#dont-use-flags-as-function-parameters">
<span class="octicon octicon-link"></span></a>از پارامتر های flag در توابع استفاده نکنید</h3>
<p dir="rtl">
پرچم ها به  شما می گویند که این تابع بیش از یک کار انجام می دهد. همونطور که قبلا گفته شد میدونیم که توابع باید
یک کار انجام دهند اگر تابع  شما مسیرهای مختلفی را دنبال می کنند ، با ساتفاده از پارامتر های منطقی و بولین خروجی تابع را  تقسیم کنید

</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
function createFile(string $name, bool $temp = false): void
{
    if ($temp) {
        touch('./temp/'.$name);
    } else {
        touch($name);
    }
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
function createFile(string $name): void
{
    touch($name);
}

function createTempFile(string $name): void
{
    touch('./temp/'.$name);
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>



<h3 id="avoid-side-effects"  dir="rtl">
<a class="anchor" name="dont-use-flags-as-function-parameters" href="#avoid-side-effects">
<span class="octicon octicon-link"></span></a>از عوارض جانبی خودداری کنید</h3>
<p dir="rtl">
یک تابع در صورت انجام کار دیگری غیر از گرفتن مقدار و بازگرداندن مقدار یا مقادیر دیگر ، یک اثر جانبی ایجاد می کند. 
یک عارضه جانبی که کاملا ناخواسته بر روند تابع شما تاثیر میگذارد  می تواند در نوشتن  یک فایل ،تغییر برخی از متغیر های گلوبال رخ دهد.
حالا ، شما نیاز دارید که عوارض جانبی آن را در یک برنامه ، گاه به گاه داشته باشید. مانند مثال قبلی ، شاید لازم باشد که در یک پرونده بنویسید 
.کاری که می خواهید انجام بدید اینه که در محلی که این کار را انجام می دهید متمرکز شوید. چندین عملکرد و کلاس وجود ندارد که در یک فایل خاص بنویسند. یک سرویس داشته باشید که آن را انجام دهد. یکی و فقط یکی 
نکته اصلی این است که از مشکلات مشترک مانند تقسیم حالت بین اشیا بدون هیچ ساختار جلوگیری کنید ، با استفاده از انواع داده های قابل تغییر که توسط همه افراد قابل نوشتن است و درمورد بروز عوارض جانبی متمرکز نیست.
اگر بتوانید این کار را انجام دهید ، از اکثریت قریب به اتفاق سایر برنامه نویسان خوشحال خواهید بود.
</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
// متغیر های گلوبال با تابع زیر ارجاعا داده میشوند
//اگر عملکرد دیگری داشتیم که از این نام استفاده می کرد ، اکنون یک آرایه است و می تواند آن را بشکند.
$name = 'Ryan McDermott';

function splitIntoFirstAndLastName(): void
{
    global $name;

    $name = explode(' ', $name);
}

splitIntoFirstAndLastName();

var_dump($name); // ['Ryan', 'McDermott'];
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
function splitIntoFirstAndLastName(string $name): array
{
    return explode(' ', $name);
}

$name = 'Ryan McDermott';
$newName = splitIntoFirstAndLastName($name);

var_dump($name); // 'Ryan McDermott';
var_dump($newName); // ['Ryan', 'McDermott'];
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="dont-write-to-global-functions"  dir="rtl">
<a class="anchor" name="dont-write-to-global-functions" href="#dont-write-to-global-functions">
<span class="octicon octicon-link"></span></a>از توابع گلوبال استفاده نکنید</h3>
<p dir="rtl">
استفاده از توابع گلوبال ایده بسیار بدیه که متاسفانه تو خیلی از زبون های برنامه نویسی ما شاهدش هستیم ، 
استفاده از این توابع ممکنه با توابع از پیش ساخته شده قبلی توی برنامه دچار تداخل بشه ، و مشکل بوجود بیاره ،
بعنوان مثال فرض کنیم شما میخواید یک تابع گلوبال با عنوان  `config()` به قطعه برنامتون اضافه کنید 
اما این ممکنه با تابعی از یک کتابخونه دیگر دچار مشکل شود.
</p>

<p dir="rtl"><strong>بد:</strong></p>

```php
function config(): array
{
    return  [
        'foo' => 'bar',
    ]
}
```
<p dir="rtl"><strong>خوب:</strong></p>


```php
class Configuration
{
    private $configuration = [];

    public function __construct(array $configuration)
    {
        $this->configuration = $configuration;
    }

    public function get(string $key): ?string
    {
        return isset($this->configuration[$key]) ? $this->configuration[$key] : null;
    }
}
```

فرخوانی کلاس `Configuration` و ایجاد یک مقدار از آن
```php
$configuration = new Configuration([
    'foo' => 'bar',
]);
```
حالا شما برای استفاده از این مقدار باید کلاس `Configuration` توی برنامتون فراخوانی کنید

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="dont-use-a-singleton-pattern"  dir="rtl">
<a class="anchor" name="dont-use-a-singleton-pattern" href="#dont-use-a-singleton-pattern">
<span class="octicon octicon-link"></span></a> از دیزاین پترن `singleton`  استفاده نکنید
</h3>
<p dir="rtl">
دیزاین پترن سینگلتون یک آنتی پترنه [anti-pattern](https://en.wikipedia.org/wiki/Singleton_pattern).  ازبیانات آقای برایان باتن : 
1 . اینها معمولا بعنوان **مقادیر گلوبال** استفاده میشوند ، حالا این مشکلش چیه ؟ بدلیل اینکه با این کار شما **دیپندسی و وابستگی های** برنامتون رو پنهان میکنید ، در عوض به جای اینکه آنها را از کلاس های رابط و اینترفیس به برنامه پاس بدهیم ، چیزهایی رو باید گلوبال کنیم تا از بد خطی جلوگیری کنیم [code smell](https://en.wikipedia.org/wiki/Code_smell).
 2. اینها قانون اصول  سالید را لغو میکنند [single responsibility principle](#single-responsibility-principle-srp): به موجب این واقعیت که **این نوع توابع به تنهایی چرخه حیات خودشون رو شکل میدهند**.
 3. آنها ذاتاً باعث می شوند که کد فشرده باشد [coupled](https://en.wikipedia.org/wiki/Coupling_%28computer_programming%29). این باعث می شود آنها را جعل کنید**تست این توابع نسبتا دشوار است** در بیشتر موارد.
 4. آنها حالت را در طول عمر برنامه حمل می کنند. یک ضربه مهم دیگر برای تست زدن از ** شما می توانید در شرایطی به نتیجه برسید که تست ها باید سفارش داده شوند ** که امتیاز بزرگی برای تست های واحدی نیست. چرا؟ زیرا هر آزمون واحد باید از دیگری مستقل باشد.

نکات خوبی هم ایشون توی این بلاگ عنوان کرده آقای [میسکو هاروی](http://misko.hevery.com/about/) در مورد [ریشه مشکلات](http://misko.hevery.com/2008/08/25/root-cause-of-singletons/).
</p>
<p dir="rtl"><strong>بد:</strong></p>

```php
class DBConnection
{
    private static $instance;

    private function __construct(string $dsn)
    {
        // ...
    }

    public static function getInstance(): DBConnection
    {
        if (self::$instance === null) {
            self::$instance = new self();
        }

        return self::$instance;
    }

    // ...
}

$singleton = DBConnection::getInstance();
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
class DBConnection
{
    public function __construct(string $dsn)
    {
        // ...
    }

     // ...
}
```


<p dir="rtl">
ایجاد یک مقدار از کلاس`DBConnection` و کانفیگ کردن آن با  [DSN](http://php.net/manual/en/pdo.construct.php#refsect1-pdo.construct-parameters).
</p>


```php
$connection = new DBConnection($dsn);
```

<p dir="rtl">
و حالا شما باید از مقدار کلاس `DBConnection` در برنامه استفاده کنید
</p>

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="encapsulate-conditionals"  dir="rtl">
<a class="anchor" name="encapsulate-conditionals" href="#encapsulate-conditionals">
<span class="octicon octicon-link"></span></a> 
شرطی هارا کپسوله کنید
</h3>
<p dir="rtl"><strong>بد:</strong></p>

```php
if ($article->state === 'published') {
    // ...
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
if ($article->isPublished()) {
    // ...
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-negative-conditionals"  dir="rtl">
<a class="anchor" name="avoid-negative-conditionals" href="#avoid-negative-conditionals">
<span class="octicon octicon-link"></span></a> 
از شرطی ها منفی خود داری کنید
</h3>

<p dir="rtl"><strong>بد:</strong></p>

```php
function isDOMNodeNotPresent(\DOMNode $node): bool
{
    // ...
}

if (!isDOMNodeNotPresent($node))
{
    // ...
}
```

<p dir="rtl"><strong>خوب:</strong></p>

```php
function isDOMNodePresent(\DOMNode $node): bool
{
    // ...
}

if (isDOMNodePresent($node)) {
    // ...
}
```

<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

### Avoid conditionals

This seems like an impossible task. Upon first hearing this, most people say,
"how am I supposed to do anything without an `if` statement?" The answer is that
you can use polymorphism to achieve the same task in many cases. The second
question is usually, "well that's great but why would I want to do that?" The
answer is a previous clean code concept we learned: a function should only do
one thing. When you have classes and functions that have `if` statements, you
are telling your user that your function does more than one thing. Remember,
just do one thing.
<p dir="rtl"><strong><a href="#table-of-contents">⬆ بازگشت به بالا</a></strong></p>

<h3 id="avoid-conditionals"  dir="rtl">
<a class="anchor" name="avoid-conditionals" href="#avoid-conditionals">
<span class="octicon octicon-link"></span></a> 
از شرطی ها منفی خود داری کنید
</h3>
<p dir="rtl">
به نظر می رسد این یک کار غیرممکن است. با شنیدن این حرف ، اکثر مردم می گویند ، "چگونه قرار است بدون دستور" if "کاری انجام دهم؟
پاسخ این است که شما می توانید برای رسیدن به همان کار در بسیاری از موارد از چند شکلی استفاده کنید
سوال دوم معمولاً این است ، "خوب این عالی است اما چرا من می خواهم این کار را انجام دهم؟"
پاسخ یک مفهوم کد پاک قبلی است که ما آموخته ایم: یک تابع فقط باید یک کار انجام دهد
هنگامی که کلاسها و توابع دارید که عبارت «if» دارند ، شما
به کاربر شما می گویند عملکرد شما بیش از یک کار انجام می دهد
</p>


<p dir="rtl"><strong>بد:</strong></p>

```php
class Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        switch ($this->type) {
            case '777':
                return $this->getMaxAltitude() - $this->getPassengerCount();
            case 'Air Force One':
                return $this->getMaxAltitude();
            case 'Cessna':
                return $this->getMaxAltitude() - $this->getFuelExpenditure();
        }
    }
}
```

**Good:**

```php
interface Airplane
{
    // ...

    public function getCruisingAltitude(): int;
}

class Boeing777 implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude() - $this->getPassengerCount();
    }
}

class AirForceOne implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude();
    }
}

class Cessna implements Airplane
{
    // ...

    public function getCruisingAltitude(): int
    {
        return $this->getMaxAltitude() - $this->getFuelExpenditure();
    }
}
```

**[⬆ back to top](#table-of-contents)**

### Avoid type-checking (part 1)

PHP is untyped, which means your functions can take any type of argument.
Sometimes you are bitten by this freedom and it becomes tempting to do
type-checking in your functions. There are many ways to avoid having to do this.
The first thing to consider is consistent APIs.

**Bad:**

```php
function travelToTexas($vehicle): void
{
    if ($vehicle instanceof Bicycle) {
        $vehicle->pedalTo(new Location('texas'));
    } elseif ($vehicle instanceof Car) {
        $vehicle->driveTo(new Location('texas'));
    }
}
```

**Good:**

```php
function travelToTexas(Traveler $vehicle): void
{
    $vehicle->travelTo(new Location('texas'));
}
```

**[⬆ back to top](#table-of-contents)**

### Avoid type-checking (part 2)

If you are working with basic primitive values like strings, integers, and arrays,
and you use PHP 7+ and you can't use polymorphism but you still feel the need to
type-check, you should consider
[type declaration](http://php.net/manual/en/functions.arguments.php#functions.arguments.type-declaration)
or strict mode. It provides you with static typing on top of standard PHP syntax.
The problem with manually type-checking is that doing it will require so much
extra verbiage that the faux "type-safety" you get doesn't make up for the lost
readability. Keep your PHP clean, write good tests, and have good code reviews.
Otherwise, do all of that but with PHP strict type declaration or strict mode.

**Bad:**

```php
function combine($val1, $val2): int
{
    if (!is_numeric($val1) || !is_numeric($val2)) {
        throw new \Exception('Must be of type Number');
    }

    return $val1 + $val2;
}
```

**Good:**

```php
function combine(int $val1, int $val2): int
{
    return $val1 + $val2;
}
```

**[⬆ back to top](#table-of-contents)**

### Remove dead code

Dead code is just as bad as duplicate code. There's no reason to keep it in
your codebase. If it's not being called, get rid of it! It will still be safe
in your version history if you still need it.

**Bad:**

```php
function oldRequestModule(string $url): void
{
    // ...
}

function newRequestModule(string $url): void
{
    // ...
}

$request = newRequestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```

**Good:**

```php
function requestModule(string $url): void
{
    // ...
}

$request = requestModule($requestUrl);
inventoryTracker('apples', $request, 'www.inventory-awesome.io');
```

**[⬆ back to top](#table-of-contents)**


## Objects and Data Structures

### Use object encapsulation

In PHP you can set `public`, `protected` and `private` keywords for methods. 
Using it, you can control properties modification on an object. 

* When you want to do more beyond getting an object property, you don't have
to look up and change every accessor in your codebase.
* Makes adding validation simple when doing a `set`.
* Encapsulates the internal representation.
* Easy to add logging and error handling when getting and setting.
* Inheriting this class, you can override default functionality.
* You can lazy load your object's properties, let's say getting it from a
server.

Additionally, this is part of [Open/Closed](#openclosed-principle-ocp) principle.

**Bad:**

```php
class BankAccount
{
    public $balance = 1000;
}

$bankAccount = new BankAccount();

// Buy shoes...
$bankAccount->balance -= 100;
```

**Good:**

```php
class BankAccount
{
    private $balance;

    public function __construct(int $balance = 1000)
    {
      $this->balance = $balance;
    }

    public function withdraw(int $amount): void
    {
        if ($amount > $this->balance) {
            throw new \Exception('Amount greater than available balance.');
        }

        $this->balance -= $amount;
    }

    public function deposit(int $amount): void
    {
        $this->balance += $amount;
    }

    public function getBalance(): int
    {
        return $this->balance;
    }
}

$bankAccount = new BankAccount();

// Buy shoes...
$bankAccount->withdraw($shoesPrice);

// Get balance
$balance = $bankAccount->getBalance();
```

**[⬆ back to top](#table-of-contents)**

### Make objects have private/protected members

* `public` methods and properties are most dangerous for changes, because some outside code may easily rely on them and you can't control what code relies on them. **Modifications in class are dangerous for all users of class.**
* `protected` modifier are as dangerous as public, because they are available in scope of any child class. This effectively means that difference between public and protected is only in access mechanism, but encapsulation guarantee remains the same. **Modifications in class are dangerous for all descendant classes.**
* `private` modifier guarantees that code is **dangerous to modify only in boundaries of single class** (you are safe for modifications and you won't have [Jenga effect](http://www.urbandictionary.com/define.php?term=Jengaphobia&defid=2494196)).

Therefore, use `private` by default and `public/protected` when you need to provide access for external classes.

For more informations you can read the [blog post](http://fabien.potencier.org/pragmatism-over-theory-protected-vs-private.html) on this topic written by [Fabien Potencier](https://github.com/fabpot).

**Bad:**

```php
class Employee
{
    public $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }
}

$employee = new Employee('John Doe');
echo 'Employee name: '.$employee->name; // Employee name: John Doe
```

**Good:**

```php
class Employee
{
    private $name;

    public function __construct(string $name)
    {
        $this->name = $name;
    }

    public function getName(): string
    {
        return $this->name;
    }
}

$employee = new Employee('John Doe');
echo 'Employee name: '.$employee->getName(); // Employee name: John Doe
```

**[⬆ back to top](#table-of-contents)**

## Classes

### Prefer composition over inheritance

As stated famously in [*Design Patterns*](https://en.wikipedia.org/wiki/Design_Patterns) by the Gang of Four,
you should prefer composition over inheritance where you can. There are lots of
good reasons to use inheritance and lots of good reasons to use composition.
The main point for this maxim is that if your mind instinctively goes for
inheritance, try to think if composition could model your problem better. In some
cases it can.

You might be wondering then, "when should I use inheritance?" It
depends on your problem at hand, but this is a decent list of when inheritance
makes more sense than composition:

1. Your inheritance represents an "is-a" relationship and not a "has-a"
relationship (Human->Animal vs. User->UserDetails).
2. You can reuse code from the base classes (Humans can move like all animals).
3. You want to make global changes to derived classes by changing a base class.
(Change the caloric expenditure of all animals when they move).

**Bad:**

```php
class Employee 
{
    private $name;
    private $email;

    public function __construct(string $name, string $email)
    {
        $this->name = $name;
        $this->email = $email;
    }

    // ...
}

// Bad because Employees "have" tax data. 
// EmployeeTaxData is not a type of Employee

class EmployeeTaxData extends Employee 
{
    private $ssn;
    private $salary;
    
    public function __construct(string $name, string $email, string $ssn, string $salary)
    {
        parent::__construct($name, $email);

        $this->ssn = $ssn;
        $this->salary = $salary;
    }

    // ...
}
```

**Good:**

```php
class EmployeeTaxData 
{
    private $ssn;
    private $salary;

    public function __construct(string $ssn, string $salary)
    {
        $this->ssn = $ssn;
        $this->salary = $salary;
    }

    // ...
}

class Employee 
{
    private $name;
    private $email;
    private $taxData;

    public function __construct(string $name, string $email)
    {
        $this->name = $name;
        $this->email = $email;
    }

    public function setTaxData(string $ssn, string $salary)
    {
        $this->taxData = new EmployeeTaxData($ssn, $salary);
    }

    // ...
}
```

**[⬆ back to top](#table-of-contents)**

### Avoid fluent interfaces

A [Fluent interface](https://en.wikipedia.org/wiki/Fluent_interface) is an object
oriented API that aims to improve the readability of the source code by using
[Method chaining](https://en.wikipedia.org/wiki/Method_chaining).

While there can be some contexts, frequently builder objects, where this
pattern reduces the verbosity of the code (for example the [PHPUnit Mock Builder](https://phpunit.de/manual/current/en/test-doubles.html)
or the [Doctrine Query Builder](http://docs.doctrine-project.org/projects/doctrine-dbal/en/latest/reference/query-builder.html)),
more often it comes at some costs:

1. Breaks [Encapsulation](https://en.wikipedia.org/wiki/Encapsulation_%28object-oriented_programming%29).
2. Breaks [Decorators](https://en.wikipedia.org/wiki/Decorator_pattern).
3. Is harder to [mock](https://en.wikipedia.org/wiki/Mock_object) in a test suite.
4. Makes diffs of commits harder to read.

For more informations you can read the full [blog post](https://ocramius.github.io/blog/fluent-interfaces-are-evil/)
on this topic written by [Marco Pivetta](https://github.com/Ocramius).

**Bad:**

```php
class Car
{
    private $make = 'Honda';
    private $model = 'Accord';
    private $color = 'white';

    public function setMake(string $make): self
    {
        $this->make = $make;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function setModel(string $model): self
    {
        $this->model = $model;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function setColor(string $color): self
    {
        $this->color = $color;

        // NOTE: Returning this for chaining
        return $this;
    }

    public function dump(): void
    {
        var_dump($this->make, $this->model, $this->color);
    }
}

$car = (new Car())
  ->setColor('pink')
  ->setMake('Ford')
  ->setModel('F-150')
  ->dump();
```

**Good:**

```php
class Car
{
    private $make = 'Honda';
    private $model = 'Accord';
    private $color = 'white';

    public function setMake(string $make): void
    {
        $this->make = $make;
    }

    public function setModel(string $model): void
    {
        $this->model = $model;
    }

    public function setColor(string $color): void
    {
        $this->color = $color;
    }

    public function dump(): void
    {
        var_dump($this->make, $this->model, $this->color);
    }
}

$car = new Car();
$car->setColor('pink');
$car->setMake('Ford');
$car->setModel('F-150');
$car->dump();
```

**[⬆ back to top](#table-of-contents)**

### Prefer final classes

The `final` should be used whenever possible:

1. It prevents uncontrolled inheritance chain.
2. It encourages [composition](#prefer-composition-over-inheritance).
3. It encourages the [Single Responsibility Pattern](#single-responsibility-principle-srp).
4. It encourages developers to use your public methods instead of extending the class to get access on protected ones.
5. It allows you to change your code without any break of applications that use your class.

The only condition is that your class should implement an interface and no other public methods are defined.

For more informations you can read [the blog post](https://ocramius.github.io/blog/when-to-declare-classes-final/) on this topic written by [Marco Pivetta (Ocramius)](https://ocramius.github.io/).

**Bad:**

```php
final class Car
{
    private $color;
    
    public function __construct($color)
    {
        $this->color = $color;
    }
    
    /**
     * @return string The color of the vehicle
     */
    public function getColor() 
    {
        return $this->color;
    }
}
```

**Good:**

```php
interface Vehicle
{
    /**
     * @return string The color of the vehicle
     */
    public function getColor();
}

final class Car implements Vehicle
{
    private $color;
    
    public function __construct($color)
    {
        $this->color = $color;
    }
    
    /**
     * {@inheritdoc}
     */
    public function getColor() 
    {
        return $this->color;
    }
}
```

**[⬆ back to top](#table-of-contents)**

## SOLID

**SOLID** is the mnemonic acronym introduced by Michael Feathers for the first five principles named by Robert Martin, which meant five basic principles of object-oriented programming and design.

 * [S: Single Responsibility Principle (SRP)](#single-responsibility-principle-srp)
 * [O: Open/Closed Principle (OCP)](#openclosed-principle-ocp)
 * [L: Liskov Substitution Principle (LSP)](#liskov-substitution-principle-lsp)
 * [I: Interface Segregation Principle (ISP)](#interface-segregation-principle-isp)
 * [D: Dependency Inversion Principle (DIP)](#dependency-inversion-principle-dip)

### Single Responsibility Principle (SRP)

As stated in Clean Code, "There should never be more than one reason for a class
to change". It's tempting to jam-pack a class with a lot of functionality, like
when you can only take one suitcase on your flight. The issue with this is
that your class won't be conceptually cohesive and it will give it many reasons
to change. Minimizing the amount of times you need to change a class is important.
It's important because if too much functionality is in one class and you modify a piece of it,
it can be difficult to understand how that will affect other dependent modules in
your codebase.

**Bad:**

```php
class UserSettings
{
    private $user;

    public function __construct(User $user)
    {
        $this->user = $user;
    }

    public function changeSettings(array $settings): void
    {
        if ($this->verifyCredentials()) {
            // ...
        }
    }

    private function verifyCredentials(): bool
    {
        // ...
    }
}
```

**Good:**

```php
class UserAuth 
{
    private $user;

    public function __construct(User $user)
    {
        $this->user = $user;
    }
    
    public function verifyCredentials(): bool
    {
        // ...
    }
}

class UserSettings 
{
    private $user;
    private $auth;

    public function __construct(User $user) 
    {
        $this->user = $user;
        $this->auth = new UserAuth($user);
    }

    public function changeSettings(array $settings): void
    {
        if ($this->auth->verifyCredentials()) {
            // ...
        }
    }
}
```

**[⬆ back to top](#table-of-contents)**

### Open/Closed Principle (OCP)

As stated by Bertrand Meyer, "software entities (classes, modules, functions,
etc.) should be open for extension, but closed for modification." What does that
mean though? This principle basically states that you should allow users to
add new functionalities without changing existing code.

**Bad:**

```php
abstract class Adapter
{
    protected $name;

    public function getName(): string
    {
        return $this->name;
    }
}

class AjaxAdapter extends Adapter
{
    public function __construct()
    {
        parent::__construct();

        $this->name = 'ajaxAdapter';
    }
}

class NodeAdapter extends Adapter
{
    public function __construct()
    {
        parent::__construct();

        $this->name = 'nodeAdapter';
    }
}

class HttpRequester
{
    private $adapter;

    public function __construct(Adapter $adapter)
    {
        $this->adapter = $adapter;
    }

    public function fetch(string $url): Promise
    {
        $adapterName = $this->adapter->getName();

        if ($adapterName === 'ajaxAdapter') {
            return $this->makeAjaxCall($url);
        } elseif ($adapterName === 'httpNodeAdapter') {
            return $this->makeHttpCall($url);
        }
    }

    private function makeAjaxCall(string $url): Promise
    {
        // request and return promise
    }

    private function makeHttpCall(string $url): Promise
    {
        // request and return promise
    }
}
```

**Good:**

```php
interface Adapter
{
    public function request(string $url): Promise;
}

class AjaxAdapter implements Adapter
{
    public function request(string $url): Promise
    {
        // request and return promise
    }
}

class NodeAdapter implements Adapter
{
    public function request(string $url): Promise
    {
        // request and return promise
    }
}

class HttpRequester
{
    private $adapter;

    public function __construct(Adapter $adapter)
    {
        $this->adapter = $adapter;
    }

    public function fetch(string $url): Promise
    {
        return $this->adapter->request($url);
    }
}
```

**[⬆ back to top](#table-of-contents)**

### Liskov Substitution Principle (LSP)

This is a scary term for a very simple concept. It's formally defined as "If S
is a subtype of T, then objects of type T may be replaced with objects of type S
(i.e., objects of type S may substitute objects of type T) without altering any
of the desirable properties of that program (correctness, task performed,
etc.)." That's an even scarier definition.

The best explanation for this is if you have a parent class and a child class,
then the base class and child class can be used interchangeably without getting
incorrect results. This might still be confusing, so let's take a look at the
classic Square-Rectangle example. Mathematically, a square is a rectangle, but
if you model it using the "is-a" relationship via inheritance, you quickly
get into trouble.

**Bad:**

```php
class Rectangle
{
    protected $width = 0;
    protected $height = 0;

    public function setWidth(int $width): void
    {
        $this->width = $width;
    }

    public function setHeight(int $height): void
    {
        $this->height = $height;
    }

    public function getArea(): int
    {
        return $this->width * $this->height;
    }
}

class Square extends Rectangle
{
    public function setWidth(int $width): void
    {
        $this->width = $this->height = $width;
    }

    public function setHeight(int $height): void
    {
        $this->width = $this->height = $height;
    }
}

function printArea(Rectangle $rectangle): void
{
    $rectangle->setWidth(4);
    $rectangle->setHeight(5);
 
    // BAD: Will return 25 for Square. Should be 20.
    echo sprintf('%s has area %d.', get_class($rectangle), $rectangle->getArea()).PHP_EOL;
}

$rectangles = [new Rectangle(), new Square()];

foreach ($rectangles as $rectangle) {
    printArea($rectangle);
}
```

**Good:**

The best way is separate the quadrangles and allocation of a more general subtype for both shapes.

Despite the apparent similarity of the square and the rectangle, they are different.
A square has much in common with a rhombus, and a rectangle with a parallelogram, but they are not subtype.
A square, a rectangle, a rhombus and a parallelogram are separate shapes with their own properties, albeit similar.

```php
interface Shape
{
    public function getArea(): int;
}

class Rectangle implements Shape
{
    private $width = 0;
    private $height = 0;

    public function __construct(int $width, int $height)
    {
        $this->width = $width;
        $this->height = $height;
    }

    public function getArea(): int
    {
        return $this->width * $this->height;
    }
}

class Square implements Shape
{
    private $length = 0;

    public function __construct(int $length)
    {
        $this->length = $length;
    }

    public function getArea(): int
    {
        return $this->length ** 2;
    }
}

function printArea(Shape $shape): void
{
    echo sprintf('%s has area %d.', get_class($shape), $shape->getArea()).PHP_EOL;
}

$shapes = [new Rectangle(4, 5), new Square(5)];

foreach ($shapes as $shape) {
    printArea($shape);
}
```

**[⬆ back to top](#table-of-contents)**

### Interface Segregation Principle (ISP)

ISP states that "Clients should not be forced to depend upon interfaces that
they do not use." 

A good example to look at that demonstrates this principle is for
classes that require large settings objects. Not requiring clients to set up
huge amounts of options is beneficial, because most of the time they won't need
all of the settings. Making them optional helps prevent having a "fat interface".

**Bad:**

```php
interface Employee
{
    public function work(): void;

    public function eat(): void;
}

class HumanEmployee implements Employee
{
    public function work(): void
    {
        // ....working
    }

    public function eat(): void
    {
        // ...... eating in lunch break
    }
}

class RobotEmployee implements Employee
{
    public function work(): void
    {
        //.... working much more
    }

    public function eat(): void
    {
        //.... robot can't eat, but it must implement this method
    }
}
```

**Good:**

Not every worker is an employee, but every employee is a worker.

```php
interface Workable
{
    public function work(): void;
}

interface Feedable
{
    public function eat(): void;
}

interface Employee extends Feedable, Workable
{
}

class HumanEmployee implements Employee
{
    public function work(): void
    {
        // ....working
    }

    public function eat(): void
    {
        //.... eating in lunch break
    }
}

// robot can only work
class RobotEmployee implements Workable
{
    public function work(): void
    {
        // ....working
    }
}
```

**[⬆ back to top](#table-of-contents)**

### Dependency Inversion Principle (DIP)

This principle states two essential things:
1. High-level modules should not depend on low-level modules. Both should
depend on abstractions.
2. Abstractions should not depend upon details. Details should depend on
abstractions.

This can be hard to understand at first, but if you've worked with PHP frameworks (like Symfony), you've seen an implementation of this principle in the form of Dependency
Injection (DI). While they are not identical concepts, DIP keeps high-level
modules from knowing the details of its low-level modules and setting them up.
It can accomplish this through DI. A huge benefit of this is that it reduces
the coupling between modules. Coupling is a very bad development pattern because
it makes your code hard to refactor.

**Bad:**

```php
class Employee
{
    public function work(): void
    {
        // ....working
    }
}

class Robot extends Employee
{
    public function work(): void
    {
        //.... working much more
    }
}

class Manager
{
    private $employee;

    public function __construct(Employee $employee)
    {
        $this->employee = $employee;
    }

    public function manage(): void
    {
        $this->employee->work();
    }
}
```

**Good:**

```php
interface Employee
{
    public function work(): void;
}

class Human implements Employee
{
    public function work(): void
    {
        // ....working
    }
}

class Robot implements Employee
{
    public function work(): void
    {
        //.... working much more
    }
}

class Manager
{
    private $employee;

    public function __construct(Employee $employee)
    {
        $this->employee = $employee;
    }

    public function manage(): void
    {
        $this->employee->work();
    }
}
```

**[⬆ back to top](#table-of-contents)**

## Don’t repeat yourself (DRY)

Try to observe the [DRY](https://en.wikipedia.org/wiki/Don%27t_repeat_yourself) principle.

Do your absolute best to avoid duplicate code. Duplicate code is bad because 
it means that there's more than one place to alter something if you need to 
change some logic.

Imagine if you run a restaurant and you keep track of your inventory: all your 
tomatoes, onions, garlic, spices, etc. If you have multiple lists that
you keep this on, then all have to be updated when you serve a dish with
tomatoes in them. If you only have one list, there's only one place to update!

Often you have duplicate code because you have two or more slightly
different things, that share a lot in common, but their differences force you
to have two or more separate functions that do much of the same things. Removing 
duplicate code means creating an abstraction that can handle this set of different 
things with just one function/module/class.

Getting the abstraction right is critical, that's why you should follow the
SOLID principles laid out in the [Classes](#classes) section. Bad abstractions can be
worse than duplicate code, so be careful! Having said this, if you can make
a good abstraction, do it! Don't repeat yourself, otherwise you'll find yourself 
updating multiple places any time you want to change one thing.

**Bad:**

```php
function showDeveloperList(array $developers): void
{
    foreach ($developers as $developer) {
        $expectedSalary = $developer->calculateExpectedSalary();
        $experience = $developer->getExperience();
        $githubLink = $developer->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];

        render($data);
    }
}

function showManagerList(array $managers): void
{
    foreach ($managers as $manager) {
        $expectedSalary = $manager->calculateExpectedSalary();
        $experience = $manager->getExperience();
        $githubLink = $manager->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];

        render($data);
    }
}
```

**Good:**

```php
function showList(array $employees): void
{
    foreach ($employees as $employee) {
        $expectedSalary = $employee->calculateExpectedSalary();
        $experience = $employee->getExperience();
        $githubLink = $employee->getGithubLink();
        $data = [
            $expectedSalary,
            $experience,
            $githubLink
        ];

        render($data);
    }
}
```

**Very good:**

It is better to use a compact version of the code.

```php
function showList(array $employees): void
{
    foreach ($employees as $employee) {
        render([
            $employee->calculateExpectedSalary(),
            $employee->getExperience(),
            $employee->getGithubLink()
        ]);
    }
}
```

**[⬆ back to top](#table-of-contents)**

## Translations

This is also available in other languages:

* :cn: **Chinese:**
   * [php-cpm/clean-code-php](https://github.com/php-cpm/clean-code-php)
* :ru: **Russian:**
   * [peter-gribanov/clean-code-php](https://github.com/peter-gribanov/clean-code-php)
* :es: **Spanish:**
   * [fikoborquez/clean-code-php](https://github.com/fikoborquez/clean-code-php)
* :brazil: **Portuguese:**
   * [fabioars/clean-code-php](https://github.com/fabioars/clean-code-php)
   * [jeanjar/clean-code-php](https://github.com/jeanjar/clean-code-php/tree/pt-br)
* :thailand: **Thai:**
   * [panuwizzle/clean-code-php](https://github.com/panuwizzle/clean-code-php)
* :fr: **French:**
   * [errorname/clean-code-php](https://github.com/errorname/clean-code-php)
* :vietnam: **Vietnamese**
   * [viethuongdev/clean-code-php](https://github.com/viethuongdev/clean-code-php)
* :kr: **Korean:**
   * [yujineeee/clean-code-php](https://github.com/yujineeee/clean-code-php)
* :tr: **Turkish:**
   * [anilozmen/clean-code-php](https://github.com/anilozmen/clean-code-php)
   
**[⬆ back to top](#table-of-contents)**
