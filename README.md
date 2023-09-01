📓 Language: English | [中文](README-ZH.md)  
🎁 Check out the [Live Demo][].  
💡 See the [Migration Guide][] to learn how to migrate between breaking changes.  

<br/><br/>

<h1 align="center">Flutter Tilt</h1>

<p align="center">
  <a href="https://pub.dev/packages/flutter_tilt"><img src="https://img.shields.io/pub/v/flutter_tilt?color=3e4663&label=stable&logo=flutter" alt="stable package" /></a>
  <a href="https://pub.dev/packages/flutter_tilt"><img src="https://img.shields.io/pub/v/flutter_tilt?color=3e4663&label=dev&logo=flutter&include_prereleases" alt="dev package" /></a>
  <a href="https://pub.dev/packages/flutter_tilt/score"><img src="https://img.shields.io/pub/points/flutter_tilt?color=2E8B57&logo=flutter" alt="pub points" /></a>
  <a href="https://www.codefactor.io/repository/github/amoshuke/flutter_tilt"><img src="https://img.shields.io/codefactor/grade/github/amoshuke/flutter_tilt?color=0CAB6B&logo=codefactor" alt="CodeFactor" /></a>
  <a href="https://codecov.io/gh/AmosHuKe/flutter_tilt"><img src="https://img.shields.io/codecov/c/github/amoshuke/flutter_tilt?label=coverage&logo=codecov" alt="codecov" /></a>
  <a href="https://pub.dev/packages/flutter_tilt"><img src="https://img.shields.io/github/languages/top/amoshuke/flutter_tilt?color=00B4AB" alt="top language" /></a>
</p>

<p align="center">
  <strong >Easily Apply Tilt Parallax Hover Effects for Flutter!</strong>
</p>

<br/>

<div align="center">
  <table width="640" align="center" border="0">
    <tr>
      <td align="center" rowspan="2">
        <img width="320px" src="https://raw.githubusercontent.com/AmosHuKe/flutter_tilt/main/README/preview.gif" alt="Example Preview GIF" />
      </td>
      <td align="center">
        <img width="320" src="https://raw.githubusercontent.com/AmosHuKe/flutter_tilt/main/README/preview2.gif" alt="Example Preview GIF - Parallax image" />
      </td>
    </tr>	
    <tr>
      <td align="center">
        <img width="320" src="https://raw.githubusercontent.com/AmosHuKe/flutter_tilt/main/README/preview3-small.gif" alt="Example Preview GIF - Layout" />
      </td>
    </tr>
    <tr>
      <td align="center" colspan="2">

Check out the [Live Demo][].
      </td>
    </tr>
  </table>
</div>

<br/>

## Table of contents 🪄

<sub>

- [Features](#features-)

- [Install](#install-)

  - [Versions compatibility](#versions-compatibility-)

  - [Add package](#add-package-)

- [Sensors compatibility](#sensors-compatibility-)

  - [Platform Support](#platform-support-)

- [Simple usage](#simple-usage-)

  - [Tilt](#tilt-)

  - [Parallax](#parallax-)

- [Usage](#usage-)

  - [Tilt widget parameters][]

  - [TiltParallax widget parameters][]

  - [ChildLayout][]

  - [TiltConfig][]

  - [LightConfig][]

  - [ShadowConfig][]

- [License](#license-)

</sub>

<br/>


## Features ✨  

- 📦 Tilt effect
- 🔦 Light effect
- 💡 Shadow effect
- 👀 Parallax effect
- 📱 Gyroscope sensor support ([more](#sensors-compatibility-))
- 🧱 Multiple layouts
- 👇 Supports hover, touch and sensors events
- 🖼️ Smooth animation
- ⚙️ Many custom parameters


## Install 🎯
### Versions compatibility 🐦  

|       Flutter       | 3.0.0+ | 3.3.0+ |  
|      ---------      |:------:|:------:|  
| flutter_tilt 2.0.0+ |  ❌  |  ✅  |  
| flutter_tilt 0.0.1+ |  ✅  |  ❌  |  


### Add package 📦  

Run this command with Flutter,  

```sh
$ flutter pub add flutter_tilt
```

or add `flutter_tilt` to `pubspec.yaml` dependencies manually.  

```yaml
dependencies:
  flutter_tilt: ^latest_version
```


## Sensors compatibility 📱
### Platform support 🎈

Sensors are triggered only on these platforms.

| Android |  iOS  |  Web (HTTPS)  | macOS | Linux | Windows |  
| :-----: | :---: | :-----------: | :---: | :---: | :-----: |  
|   ✅   |   ✅  |      ✅      |   ❌  |  ❌  |    ❌   |  


## Simple usage 📖  

Example: [flutter_tilt/example][]


### Tilt 📦  

[Tilt][Tilt widget parameters] widget will have default tilt, shadow, and light effects.  

```dart
/// Import flutter_tilt
import 'package:flutter_tilt/flutter_tilt.dart';

...
Tilt(
  child: Container(
    width: 150.0,
    height: 300.0,
    color: Colors.grey,
  ),
),
... 
```


### Parallax 👀  

[TiltParallax][TiltParallax widget parameters] widget can only be used in the `childLayout` of `Tilt` widget.   

```dart
/// Import flutter_tilt
import 'package:flutter_tilt/flutter_tilt.dart';

...
Tilt(
  childLayout: const ChildLayout(
    outer: [
      /// Parallax here
      Positioned(
        child: TiltParallax(
          child: Text('Parallax'),
        ),
      ),
      /// Parallax here
      Positioned(
        top: 20.0,
        left: 20.0,
        child: TiltParallax(
          size: Offset(-10.0, -10.0),
          child: Text('Tilt'),
        ),
      ),
    ],
  ),
  child: Container(
    width: 150.0,
    height: 300.0,
    color: Colors.brown,
  ),
),
... 
```


## Usage 📖  
### `Tilt` widget parameters 🤖  

| Parameter | Type | Default | Description |  
| --- | --- | --- | --- |
| child <sup>`required`</sup> | `Widget` | - | Create a widget that its child widget can be tilted. |  
| childLayout | [ChildLayout][] | `ChildLayout()` | Other child layouts. <br/> e.g. parallax inner, outer, behind. |  
| disable | `bool` | `false` | Disable all effects. |  
| fps | `int` | `60` | Gesture triggered frames. |  
| border | `BoxBorder?` | `null` | BoxDecoration border. |  
| borderRadius | `BorderRadiusGeometry?` | `null` | BoxDecoration borderRadius. |  
| clipBehavior | `Clip` | `Clip.antiAlias` | Flutter clipBehavior. |  
| tiltConfig | [TiltConfig][] | `TiltConfig()` | Tilt effect config. |  
| lightConfig | [LightConfig][] | `LightConfig()` | Light effect config. |  
| shadowConfig | [ShadowConfig][] | `ShadowConfig()` | Shadow effect config. |  
| onGestureMove | `void Function(TiltDataModel, GesturesType)?` | `null` | Gesture move callback. |  
| onGestureLeave | `void Function(TiltDataModel, GesturesType)?` | `null` | Gesture leave callback. |  


### `TiltParallax` widget parameters 🤖  

| Parameter | Type | Default | Description |  
| --- | --- | --- | --- |
| child <sup>`required`</sup> | `Widget` | - | Create a widget with parallax. |  
| size | `Offset` | `Offset(10.0, 10.0)` | Parallax size (pixel). |  
| filterQuality | `FilterQuality` | `null` | Flutter FilterQuality. |  


### ChildLayout 📄  

| Parameter | Type | Default | Description |  
| --- | --- | --- | --- |
| outer | `List<Widget>` | `<Widget>[]` | As with Stack, you can use the Stack layout to create widgets that are outer of the child. <br/> e.g. parallax effects. |  
| inner | `List<Widget>` | `<Widget>[]` | As with Stack, you can use the Stack layout to create widgets that are inner of the child. <br/> e.g. parallax effects. |  
| behind | `List<Widget>` | `<Widget>[]` | As with Stack, you can use the Stack layout to create widgets that are behind of the child. <br/> e.g. parallax effects. |  


### TiltConfig 📄  

| Parameter | Type | Default | Description |  
| --- | --- | --- | --- |
| disable | `bool` | `false` | Only disable the tilt effect. |  
| initial | `Offset?` | `null` | Initial tilt progress, range `(x, y): (1, 1) to (-1, -1)`, <br/> you can exceed the range, but the maximum tilt angle during gesture movement is always tilted according to `[TiltConfig.angle]`. <br/> e.g. (0.0, 0.0) center <br/> (1.0, 1.0) Maximum tilt top left `[TiltConfig.angle]`. |  
| angle | `double` | `10.0` | Maximum tilt angle. <br/> e.g. 180 will flip. |  
| direction | `List<TiltDirection>?` | `null` | Tilt Direction, multiple directions, customized direction values. |  
| enableRevert | `bool` | `true` | Enable Tilt Revert, will revert to the initial state. |  
| enableReverse | `bool` | `false` | Tilt reverse, can be tilted up or down. |  
| filterQuality | `FilterQuality` | `null` | Flutter FilterQuality. |  
| enableGestureSensors | `bool` | `true` | Gyroscope sensor triggered tilt. |  
| sensorFactor | `double` | `10.0` | Sensor trigger factor (sensitivity). |  
| sensorMoveDuration | `Duration` | `Duration(milliseconds: 50)` | Animation duration during sensor move. |  
| enableGestureHover | `bool` | `true` | Hover gesture triggered tilt. |  
| enableGestureTouch | `bool` | `true` | Touch gesture triggered tilt. |  
| enableOutsideAreaMove | `bool` | `true` | Tilt can continue to be triggered outside the area. <br/> (`only when the pointer is pressed and moved`) |  
| moveDuration | `Duration` | `Duration(milliseconds: 100)` | Animation duration during gesture move (touch, hover gestures only). |  
| leaveDuration | `Duration` | `Duration(milliseconds: 300)` | Animation duration after gesture leave (touch, hover gestures only). |  
| moveCurve | `Curve` | `Curves.linear` | Animation curve during gesture move (touch, hover gestures only). |  
| leaveCurve | `Curve` | `Curves.linear` | Animation curve after gesture leave (touch, hover gestures only). |  


### LightConfig 📄  

| Parameter | Type | Default | Description |  
| --- | --- | --- | --- |
| disable | `bool` | `false` | Only disable the light effect. |  
| color | `Color` | `Color(0xFFFFFFFF)` | Light color. |  
| minIntensity | `double` | `0.0` | Color minimum opacity, also initial opacity. |  
| maxIntensity | `double` | `0.5` | Color maximum opacity for tilt progresses. |  
| direction | `LightDirection` | `LightDirection.around` | Light direction. <br/> Affects: <br/> `[ShadowConfig.direction]` (not affected after configuration). |  
| enableReverse | `bool` | `false` | Reverse light direction. <br/> Affects: <br/> `[ShadowConfig.direction]` (not affected after configuration). <br/> `[ShadowConfig.enableReverse]` (not affected after configuration). |  


### ShadowConfig 📄  

| Parameter | Type | Default | Description |  
| --- | --- | --- | --- |
| disable | `bool` | `false` | Only disable the shadow effect. |  
| color | `Color` | `Color(0xFF9E9E9E)` | Shadow color. |  
| minIntensity | `double` | `0.0` | Color minimum opacity, also initial opacity. |  
| maxIntensity | `double` | `0.5` | Color maximum opacity as tilt progresses. |  
| offsetInitial | `Offset` | `Offset(0.0, 0.0)` | Initial value of shadow offset (pixel). <br/> e.g. (0.0, 0.0) center. <br/> (40.0, 40.0) Offset 40 pixels to the top left. |  
| offsetFactor | `double` | `0.1` | Shadow offset factor, relative to current widget size. |  
| spreadInitial | `double` | `0.0` | Initial value of shadow spread radius (pixel). |  
| spreadFactor | `double` | `0.0` | Shadow spread radius factor, relative to current widget size. |  
| minBlurRadius | `double` | `10.0` | Minimum blur radius, also initial blur radius. |  
| maxBlurRadius | `double` | `20.0` | Maximum blur radius for tilt progresses. |  
| direction | `ShadowDirection?` | `null` | Shadow direction. |  
| enableReverse | `bool?` | `null` | Reverse shadow direction. |  


## License 📄  

[![MIT License](https://img.shields.io/badge/license-MIT-green)](https://github.com/AmosHuKe/flutter_tilt/blob/main/LICENSE)  
Open sourced under the MIT license.  

© AmosHuKe

[Live Demo]: https://amoshuke.github.io/flutter_tilt_book
[Migration Guide]: https://github.com/AmosHuKe/flutter_tilt/blob/main/guides/migration_guide.md
[flutter_tilt/example]: https://github.com/AmosHuKe/flutter_tilt/tree/main/example
[Tilt widget parameters]: #tilt-widget-parameters-
[TiltParallax widget parameters]: #tiltparallax-widget-parameters-
[ChildLayout]: #childlayout-
[TiltConfig]: #tiltconfig-
[LightConfig]: #lightconfig-
[ShadowConfig]: #shadowconfig-
