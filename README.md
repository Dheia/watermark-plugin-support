# Nano2.Watermark

## Introduction to the Watermark Plugin in OctoberCMS

The Watermark plugin in OctoberCMS is an innovative tool aimed at enhancing the protection of images and graphics on the web. With this plugin, users can automatically add a logo or watermark to images without the need for manual intervention, making it easier to maintain intellectual property rights.

The Watermark plugin is flexible, allowing users to customize the design of the watermark in terms of size, transparency, and position on the image. Additionally, the plugin can be easily integrated with any site built on the OctoberCMS framework, making it an ideal choice for designers, photographers, and website owners looking to protect their content.

By using this plugin, it becomes possible to provide the necessary protection for images, enhancing content value and increasing professionalism in the presentation of products and services.

## Settings for the Watermark Plugin in OctoberCMS

The Watermark plugin comes with a set of customizable settings, allowing users to adjust functionalities according to their needs. Here are the details of the main settings:

1. **Enable Automatic Watermarking with Site Logo**:
   ```plaintext
   NANO2_WATERMARK_IS_SUPPORT_WATERMARK = false
   ```
   - This setting determines whether the watermark will be automatically added to images upon upload. If the value is `true`, the feature will be enabled.

2. **Path to the Watermark Image**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_PATH = null
   ```
   - Here you can specify the path to the watermark image. If a path is not provided, the site logo will be used by default.

3. **Watermark Position**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_POSITION = 'bottom-left'
   ```
   - This setting is used to define the position of the watermark on the image. Available options include:
     - `bottom-left`
     - `bottom-right`
     - `top-right`
     - `top-left`

4. **Custom Width for the Logo**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_WIDTH = null
   ```
   - You can specify the width of the watermark here. If the value is `null`, the default width will be used.

5. **Custom Height for the Logo**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_HEIGHT = null
   ```
   - Similar to width, you can specify the height of the watermark. The default value will be used if it is `null`.

6. **Resize Logo Dimensions as a Percentage**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_RESIZE_PERCENTAGE = null
   ```
   - If you wish to adjust the dimensions of the watermark based on a percentage of the original image, you can enter the percentage here (e.g., `10` or `15`).

7. **Overlay Watermark on Original Image**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_OVERWRITE_ORIGNAL = true
   ```
   - If the value is `true`, the watermark will be written onto the original image. To create a new file with the watermark, change the value to `false`.

8. **Path for the Created Image File**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_NEW_PATH = null
   ```
   - You can specify a path to save the new image with the watermark. If it is `null`, the default path will be used.

9. **Check if the Image Already Has a Watermark**:
   ```plaintext
   NANO2_WATERMARK_WATERMARK_CHECK_EXISTS = true
   ```
   - This setting determines whether to check the image for a pre-existing watermark before adding a new one.

10. **Write to Image Metadata**:
    ```plaintext
    NANO2_WATERMARK_WATERMARK_IS_WRITE_EXIF = true
    ```
    - If the value is `true`, information will be written in the image's EXIF data indicating that a watermark has been added.

11. **Allowed Image Fields for Watermarking**:
    ```plaintext
    NANO2_WATERMARK_WATERMARK_ALLOW_FIELD = 'image,images,avatar'
    ```
    - You can specify which fields are permitted to have a watermark added, such as `image`, `images`, and `avatar`.
    - To allow all fields, use `*`.
### Summary

These settings allow users to fully customize their watermarking experience, making it easier to protect their content in a way that meets their specific needs.

## Using the WatermarkHelper Class to Add Watermarks

The Watermark plugin in OctoberCMS offers the ability to use the `Nano2\Watermark\Classes\WatermarkHelper` class, which is a powerful and useful tool for handling watermarks. Through this class, developers can implement advanced operations to dynamically add watermarks to images.

### Features of the WatermarkHelper Class:

1. **Automatic Watermark Addition**: The `WatermarkHelper` can be used to automatically add a logo or watermark to images upon upload, saving time and effort.

2. **Customization Options**: The class provides multiple options for customizing the watermark, such as:
   - **Position**: Setting the position of the watermark on the image (top, bottom, left, right).
   - **Transparency**: Adjusting the transparency level to fit the image design.
   - **Size**: Adjusting the size of the watermark to match the original image.

3. **Ease of Use**: The class has a simple interface that enables developers to easily integrate it into their projects without complexity.

### How to Use:

To add a watermark using `WatermarkHelper`, you can follow these steps:

1. **Call the Class**: First, you need to include the class in your code.
   
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

2. **Specify the Image and Watermark**: You can specify the image you want to add the watermark to, as well as the logo you want to use.

3. **Execute the Operation**: After specifying the required options, you can call the appropriate function to add the watermark.

Using `WatermarkHelper`, it becomes easy to effectively protect images, contributing to the enhancement of the quality of content presented on the site and increasing the professionalism of the brand.