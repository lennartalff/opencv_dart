# opencv_core

OpenCV for Flutter, if `highgui` or `videoio` is required, use [opencv_dart](https://pub.dev/packages/opencv_dart)

> [!IMPORTANT]
>
> OpenCV SDK (~100M) will be downloaded via `FetchContent` of cmake, you can
> set `DARTCV_CACHE_DIR` environment variable to cache it and avoid downloading it again.
> e.g., `export DARTCV_CACHE_DIR=$HOME/.cache/dartcv`

## Supported platforms

| Platform | Supported          | Tested             | Platforms                      |
| -------- | ------------------ | ------------------ | ------------------------------ |
| Android  | :white_check_mark: | :white_check_mark: | x86_64, arm64-v8a, armeabi-v7a |
| iOS      | :white_check_mark: | :white_check_mark: | arm64, x64(Simulator)          |
| Linux    | :white_check_mark: | :white_check_mark: | x64, arm64                     |
| Windows  | :white_check_mark: | :white_check_mark: | x64, arm64                     |
| macOS    | :white_check_mark: | :white_check_mark: | x64, arm64                     |

## Supported modules

[Supported modules](https://github.com/rainyl/opencv_dart?tab=readme-ov-file#status)

## Customizing OpenCV Modules

You can enable or disable specific OpenCV modules for your build by specifying them in your app's `pubspec.yaml` file.

> [!NOTE]
>
> Currently only Android, Windows, and Linux are supported.

### Example `pubspec.yaml` configuration

```yaml
# ...Your existing configuration...
hooks:
  user_defines:
    dartcv4:
      exclude_modules:
        - contrib
        - dnn
        - features2d
        - core
      include_modules:
        - core # core is always required thus will be ignored even configured here.
        - imgproc
        - videoio
```

- valid modules: `core`, `calib3d`, `contrib`, `dnn`, `features2d`, `flann`, `highgui`, `imgproc`, `imgcodecs`, `objdetect`, `photo`, `stitching`, `video`, `videoio`
- Use `exclude_modules` to disable specific modules, or `include_modules` to enable specific modules.
- If neither is specified, all modules except `highgui` will be enabled.
- also refer to [example/pubspec.yaml](https://github.com/rainyl/opencv_dart/blob/main/packages/opencv_dart/example/pubspec.yaml)

## Package Size

![opencv_dart_size_report](images/opencv_core_size_report.svg)

## Examples

see [example](https://github.com/rainyl/opencv_dart/tree/main/packages/opencv_core/example)

More examples refet to [awesome-opencv_dart](https://github.com/rainyl/awesome-opencv_dart) and share yours

## Screenshots

see [Demos](https://github.com/rainyl/opencv_dart?tab=readme-ov-file#Demos)

## License

[Apache-2.0 License](LICENSE)
