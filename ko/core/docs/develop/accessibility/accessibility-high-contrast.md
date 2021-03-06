# 고대비 색상

High contrast is used to help locate and distinguish between visual elements. Here we give some pointers for you to add support for high contrast mode.

## 고대비 색상 모드

High contrast mode is configured and managed automatically on Windows, Mac, and Linux (in some distributions). But, it is not supported by some web browsers. Chrome in Windows, for example, doesn't change the color of the web page in high contrast mode, while Edge turns the white backgrounds to black.

Because of this, we implemented a high contrast mode that is turned on manually in PXT thanks to help from a JavaScript implementation in `app.tsx`.

## 고대비 색상 관리

When high contrast is enabled, a `hc` class is added to the `root` node of the DOM. This applies the CSS from `pxt/theme/highcontrast.less` to add the contrast styles. Use this file to change the high contrast colors for the MakeCode editor.

### ~hint

The documentation and [**makecode.com**](https://makecode.com) do not have a special mode for the high contrast. They use the operating system settings.

### ~

Each target has a separate implementation to support high contrast.