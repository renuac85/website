---
title: Creating responsive and adaptive apps
description: It's important to create apps, whether for mobile or web, so that they are responsive to size and orientation changes.
short-title: Responsive and adaptive
---

{% include docs/yt_shims.liquid %}

One of Flutter's primary goals is to create a framework
that allows you to develop apps from a single codebase
that look and feel great on any platform.

This means that your app might appear on screens of
many different sizes, from a watch, to a foldable
phone with two screens, to a high def monitor.

Two terms that describe concepts for this
scenario are _adaptive_ and _responsive_. Ideally,
you'd want your app to be _both_ but what,
exactly, does this mean?
These terms are similar, but they are not the same.

## The difference between an adaptive and a responsive app

_Adaptive_ and _responsive_ can be viewed as separate
dimensions of an app: you can have an adaptive app
that is not responsive, or vice versa. And, of course,
an app can be both, or neither.

**Responsive**
: Typically, a _responsive_ app has had its layout
  tuned for the available screen size. Often this
  means (for example), re-laying out the UI if the
  user resizes the window, or changes the device's
  orientation. This is especially necessary when
  the same app can run on a variety of devices,
  from a watch, phone, tablet, to a laptop or
  desktop computer.

**Adaptive**
: _Adapting_ an app to run on different device types,
  such as mobile and desktop, requires dealing
  with mouse and keyboard input, as well as
  touch input. It also means there are different
  expectations about the app's visual density,
  how component selection works
  (cascading menus vs bottom sheets, for example),
  using platform-specific features (such as
  top-level windows), and more.

Learn more in the following 5-minute video:

<iframe width="560" height="315" src="{{yt-embed}}/HD5gYnspYzk?si=dsA37QUjHBb2Zh_-" title="Learn the difference between adaptive and responsive Flutter apps" {{yt-set}}></iframe>
[Adaptive vs Responsive][]

## Creating a responsive Flutter app

Flutter allows you to create apps that self-adapt
to the device's screen size and orientation.

There are two basic approaches to creating Flutter
apps with responsive design:

**Use the [`LayoutBuilder`][] class**
: From its [`builder`][] property, you get a
  [`BoxConstraints`][] object.
  Examine the constraint's properties to decide what to
  display. For example, if your [`maxWidth`][] is greater than
  your width breakpoint, return a [`Scaffold`][] object with a
  row that has a list on the left. If it's narrower,
  return a [`Scaffold`][] object with a drawer containing that
  list. You can also adjust your display based on the
  device's height, the aspect ratio, or some other property.
  When the constraints change (for example,
  the user rotates the phone, or puts your app into a tile UI
  on Android), the build function runs.

**Use the [`MediaQuery.of()`][] method in your build functions**
: This gives you the size, orientation, etc, of your current app.
  This is more useful if you want to make decisions based on the
  complete context rather than on just the size of your particular
  widget. Again, if you use this, then your build function automatically
  runs if the user somehow changes the app's size.

Other useful widgets and classes for creating a responsive UI:

* [`AspectRatio`][]
* [`CustomSingleChildLayout`][]
* [`CustomMultiChildLayout`][]
* [`FittedBox`][]
* [`FractionallySizedBox`][]
* [`LayoutBuilder`][]
* [`MediaQuery`][]
* [`MediaQueryData`][]
* [`OrientationBuilder`][]

### Other resources

For more information, here are a few resources,
including contributions from the Flutter community:

* [Developing for Multiple Screen Sizes and Orientations in
  Flutter][] by Deven Joshi
* [Build Responsive UIs in Flutter][] by Raouf Rahiche
* [Making Cross-platform Flutter Landing Page Responsive][]
  by Priyanka Tyagi
* [How to make flutter app responsive according to different screen
  size?][], a question on StackOverflow

[`AspectRatio`]: {{site.api}}/flutter/widgets/AspectRatio-class.html
[`BoxConstraints`]: {{site.api}}/flutter/rendering/BoxConstraints-class.html
[Build Responsive UIs in Flutter]: {{site.medium}}/flutter-community/build-responsive-uis-in-flutter-fd450bd59158
[`builder`]: {{site.api}}/flutter/widgets/LayoutBuilder/builder.html
[`CustomMultiChildLayout`]: {{site.api}}/flutter/widgets/CustomMultiChildLayout-class.html
[`CustomSingleChildLayout`]: {{site.api}}/flutter/widgets/CustomSingleChildLayout-class.html
[Developing for Multiple Screen Sizes and Orientations in Flutter]: {{site.medium}}/flutter-community/developing-for-multiple-screen-sizes-and-orientations-in-flutter-fragments-in-flutter-a4c51b849434
[`FittedBox`]: {{site.api}}/flutter/widgets/FittedBox-class.html

[`FractionallySizedBox`]: {{site.api}}/flutter/widgets/FractionallySizedBox-class.html
[How to make flutter app responsive according to different screen size?]: {{site.so}}/questions/49704497/how-to-make-flutter-app-responsive-according-to-different-screen-size
[`LayoutBuilder`]: {{site.api}}/flutter/widgets/LayoutBuilder-class.html
[Making Cross-platform Flutter Landing Page Responsive]: {{site.medium}}/flutter-community/making-cross-platform-flutter-landing-page-responsive-7fffe0655970
[`maxWidth`]: {{site.api}}/flutter/rendering/BoxConstraints/maxWidth.html
[`MediaQuery`]: {{site.api}}/flutter/widgets/MediaQuery-class.html
[`MediaQuery.of()`]: {{site.api}}/flutter/widgets/MediaQuery/of.html
[`MediaQueryData`]: {{site.api}}/flutter/widgets/MediaQueryData-class.html
[`OrientationBuilder`]: {{site.api}}/flutter/widgets/OrientationBuilder-class.html
[`Scaffold`]: {{site.api}}/flutter/material/Scaffold-class.html

## Creating an adaptive Flutter app

Learn more about creating an adaptive Flutter app with
[Building adaptive apps][], written by the gskinner team.

You might also check out the following episodes
of The Boring Show:

<iframe style="max-width: 100%" width="560" height="315" src="{{yt-embed}}/n6Awpg1MO6M" title="Learn about adaptive layouts on the Boring Show" {{yt-set}}></iframe>
[Adaptive layouts][]

<iframe style="max-width: 100%" width="560" height="315" src="{{yt-embed}}/eikOZzfc0l4" title="Continue to learn about adaptive layouts on the Boring Show" {{yt-set}}></iframe>
[Adaptive layouts, part 2][]

For an excellent example of an adaptive app,
check out Flutter Folio, a scrapbooking app created
in collaboration with gskinner and the Flutter team:

<iframe style="max-width: 100%" width="560" height="315" src="{{yt-embed}}/yytBENOnF0w" title="Watch a demonstration of the Flutter Folio app" {{yt-set}}></iframe>

The [Folio source code][] is also available on GitHub.
Learn more on the [gskinner blog][].

### Other resources

You can learn more about creating platform adaptive apps
in the following resources:

* [Platform-specific behaviors and adaptations][], a page on this site.
* [Extreme UI Adaptability in Flutter][], the story of how Google Earth is
  using Flutter to take adaptability to the next level.
* [Designing truly adaptive user interfaces][] a blog post and video by
  Aloïs Deniel, presented at the Flutter Vikings 2020 conference.

[Adaptive layouts]: {{yt-watch}}?v=n6Awpg1MO6M&t=694s
[Adaptive layouts, part 2]: {{yt-watch}}?v=eikOZzfc0l4&t=11s
[Adaptive vs Responsive]: {{site.youtube-site}}/HD5gYnspYzk?si=5ItDD7UjXvGCRM0K
[Building adaptive apps]: {{site.url}}/ui/layout/responsive/building-adaptive-apps

[Designing truly adaptive user interfaces]: https://www.aloisdeniel.com/blog/designing-truly-adaptative-user-interfaces
[Folio source code]: {{site.github}}/gskinnerTeam/flutter-folio
[gskinner blog]: https://blog.gskinner.com/
[Platform-specific behaviors and adaptations]: {{site.url}}/platform-integration/platform-adaptations
[Extreme UI Adaptability in Flutter]: {{site.flutter-medium}}/extreme-ui-adaptability-in-flutter-how-google-earth-supports-every-use-case-on-earth-6db4661e7a17
