# Nano2.Watermark

## مقدمة عن إضافة Watermark في OctoberCMS

تُعتبر إضافة Watermark في OctoberCMS أداة مبتكرة تهدف إلى تعزيز حماية الصور والرسوم البيانية على الويب. من خلال هذه الإضافة، يمكن للمستخدمين إضافة شعار أو علامة مائية إلى الصور بشكل تلقائي ودون الحاجة لتدخل يدوي، مما يسهل عملية الحفاظ على حقوق الملكية الفكرية.

تتميز إضافة Watermark بالمرونة، حيث يمكن تخصيص تصميم العلامة المائية، سواء من حيث الحجم، والشفافية، والموقع على الصورة. بالإضافة إلى ذلك، يمكن تكامل الإضافة بسهولة مع أي موقع يعتمد على نظام OctoberCMS، مما يجعلها خيارًا مثاليًا للمصممين، والمصورين، وأصحاب المواقع الإلكترونية الراغبين في حماية محتواهم.

باستخدام هذه الإضافة، يصبح من الممكن توفير الحماية اللازمة للصور، مما يعزز من قيمة المحتوى ويزيد من الاحترافية في عرض المنتجات والخدمات.


## الإعدادات الخاصة بإضافة Watermark في OctoberCMS

تأتي إضافة Watermark مع مجموعة من الإعدادات القابلة للتخصيص، مما يتيح للمستخدمين ضبط الوظائف وفقًا لاحتياجاتهم. فيما يلي تفاصيل حول الإعدادات الرئيسية:

1. **تفعيل خاصية إضافة علامة مائية بشعار الموقع إلى الصور بشكل تلقائي**:
   ```plaintext
   NANO2_WATERMARK_IS_SUPPORT_WATERMARK = false
   ```
   - هذه الإعدادات تُحدد ما إذا كانت العلامة المائية ستضاف تلقائيًا إلى الصور عند رفعها. إذا كانت القيمة `true`، سيتم تفعيل الخاصية.

2. **مسار صورة العلامة المائية**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_PATH = null
   ```
   - هنا يمكنك تحديد مسار صورة العلامة المائية. إذا لم يتم توفير مسار، سيتم اعتماد شعار الموقع افتراضيًا.

3. **موضع العلامة المائية**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_POSITION = 'bottom-left'
   ```
   - يُستخدم لتحديد مكان وضع العلامة المائية على الصورة. الخيارات المتاحة تشمل:
     - `bottom-left`
     - `bottom-right`
     - `top-right`
     - `top-left`

4. **عرض مخصص للشعار**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_WIDTH = null
   ```
   - يمكنك تحديد عرض العلامة المائية هنا. إذا كانت القيمة `null`، سيتم استخدام العرض الافتراضي.

5. **ارتفاع مخصص للشعار**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_HEIGHT = null
   ```
   - مثل العرض، يمكنك تحديد ارتفاع العلامة المائية. القيمة الافتراضية ستُستخدم إذا كانت `null`.

6. **احتساب أبعاد الشعار بالنسبة المئوية**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_RESIZE_PERCENTAGE = null
   ```
   - إذا كنت ترغب في ضبط أبعاد العلامة المائية بناءً على نسبة مئوية من الصورة الأصلية، يمكنك إدخال النسبة المئوية هنا (مثل `10` أو `15`).

7. **وضع العلامة على ملف الصورة الأصلية**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_OVERWRITE_ORIGNAL = true
   ```
   - إذا كانت القيمة `true`، سيتم كتابة العلامة المائية على الصورة الأصلية. إذا كنت ترغب في إنشاء ملف جديد بالصورة مع العلامة، قم بتغيير القيمة إلى `false`.

8. **مسار ملف الصورة المنشأة**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_NEW_PATH = null
   ```
   - يمكنك تحديد مسار لحفظ الصورة الجديدة مع العلامة المائية. إذا كانت `null`, سيتم استخدام المسار الافتراضي.

9. **فحص ما إذا كانت الصورة تحتوي على علامة مائية من قبل**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_CHECK_EXISTS = true
   ```
   - هذه الإعدادة تحدد ما إذا كان يجب فحص الصورة لوجود علامة مائية مسبقة قبل إضافة علامة جديدة.

10. **الكتابة على بيانات الصورة**:
    ```plaintext
    NANO2_WATERMARK_WATERMARK_IS_WRITE_EXIF = true
    ```
    - إذا كانت القيمة `true`, سيتم كتابة معلومات في بيانات EXIF للصورة تشير إلى أنه قد تم إضافة علامة مائية.

11. **أسماء حقول الصور المسموح بإضافة علامة مائية لها**:
    ```plaintext
    NANO2_WATERMARK_WATERMARK_ALLOW_FIELD = 'image,images,avatar'
    ```
    - يمكنك تحديد الحقول التي يُسمح بإضافة العلامة المائية إليها، مثل `image`, `images`, و `avatar`.
    - للسماح بكافة الحقول `*`

### خلاصة

تتيح هذه الإعدادات للمستخدمين تخصيص تجربة إضافة العلامات المائية بشكل كامل، مما يسهل عليهم حماية محتواهم بطريقة تتناسب مع احتياجاتهم الخاصة.


## استخدام كلاس WatermarkHelper لإضافة العلامة المائية

تقدم إضافة Watermark في OctoberCMS إمكانية استخدام الكلاس `Nano2\Watermark\Classes\WatermarkHelper`، الذي يعد أداة قوية ومفيدة للتعامل مع العلامات المائية. من خلال هذا الكلاس، يمكن للمطورين تنفيذ عمليات متقدمة لإضافة العلامة المائية إلى الصور بشكل ديناميكي.

### ميزات كلاس WatermarkHelper:

1. **إضافة العلامة المائية بشكل تلقائي**: يمكن استخدام `WatermarkHelper` لإضافة الشعار أو علامة مائية إلى الصور بشكل أوتوماتيكي عند تحميلها، مما يوفر الوقت والجهد.

2. **خيارات التخصيص**: يوفر الكلاس خيارات متعددة لتخصيص العلامة المائية، مثل:
   - **الموقع**: تحديد موضع العلامة المائية على الصورة (أعلى، أسفل، يمين، يسار).
   - **الشفافية**: تعديل مستوى الشفافية لتناسب تصميم الصورة.
   - **الحجم**: إمكانية ضبط حجم العلامة المائية لتكون متناسبة مع الصورة الأصلية.

3. **سهولة الاستخدام**: يتمتع الكلاس بواجهة استخدام بسيطة تمكن المطورين من دمجه بسهولة في مشاريعهم دون التعقيد.

### كيفية الاستخدام:

لإضافة علامة مائية باستخدام `WatermarkHelper`، يمكن اتباع الخطوات التالية:

1. **استدعاء الكلاس**: يجب أولاً استدعاء الكلاس في الكود الخاص بك.
   
```php
   use Input;
   use Nano2\Watermark\Classes\WatermarkHelper;

   $watermarkPath = Input::get('watermarkPath', null);
   $position = Input::get('position', 'bottom-right');
   $newWidth = Input::get('newWidth', null);
   $newHeight = Input::get('newHeight', null);
   $resizePercentage = Input::get('resizePercentage', null);
   $overwriteOriginal = Input::get('overwriteOriginal', true);
   $newImagePath = Input::get('newImagePath', null);
   $checkWatermarkExists = Input::get('checkWatermarkExists', true);
   $isWriteExifWatermark = Input::get('isWriteExifWatermark', true);
   
   $result = \Nano\Helpers\Classes\Helpers\WatermarkHelper::processImage($path, $watermarkPath, $position, $newWidth, $newHeight, $resizePercentage, $overwriteOriginal, $newImagePath, $checkWatermarkExists, $isWriteExifWatermark);
   
   //output $result
   /*
   [
        "status" => true,
        "message" => "نجحة العملية  ",
        "error" => null,
        "input_data" => [
            "imagePath" => "storage/app/uploads/public/66b/e30/ff9/66be30ff97da3334316351.jpg",
            "watermarkPath" => null,
            "position" => "bottom-left",
            "newWidth" => null,
            "newHeight" => null,
            "resizePercentage" => "20",
            "overwriteOriginal" => true,
            "newImagePath" => null,
            "checkWatermarkExists" => true,
            "isWriteExifWatermark" => true
        ],
        "process_data" => [
            "imagePath" => "storage/app/uploads/public/66b/e30/ff9/66be30ff97da3334316351.jpg",
            "watermarkPath" => "/home/u304577476/domains/now-ye.com/public_html/account/plugins/tss/basic/assets/images/logo.png",
            "newImagePath" => null,
            "saveImagePath" => "storage/app/uploads/public/66b/e30/ff9/66be30ff97da3334316351.jpg",
            "position" => "bottom-left",
            "newWidth" => null,
            "newHeight" => null,
            "resizePercentage" => "20",
            "overwriteOriginal" => true,
            "checkWatermarkExists" => true,
            "isWriteExifWatermark" => true
        ]
    ]
   */
   
```

2. **تحديد الصورة والعلامة المائية**: يمكنك تحديد الصورة التي ترغب في إضافة العلامة المائية إليها، وكذلك الشعار الذي تريد استخدامه.

3. **تنفيذ العملية**: بعد تحديد الخيارات المطلوبة، يمكنك استدعاء الدالة المناسبة لإضافة العلامة المائية.

باستخدام `WatermarkHelper`، يصبح من السهل ضمان حماية الصور بشكل فعال، مما يسهم في تعزيز جودة المحتوى المقدم على الموقع ويزيد من احترافية العلامة التجارية.

