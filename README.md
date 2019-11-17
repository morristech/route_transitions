# Route transitions
A flutter library containing useful animations for routing . <br/>
<img src="./media/ios.gif" height="300" alt="ios" />
<img src="./media/android.gif" height="300" alt="android" />

# Usage
```dart
import 'package:route_transitions/route_transitions.dart'; // Add this
...
onPressed: () {
  Navigator.of(context).push(PageRouteTransition( // Main animation class
      animationType: AnimationType.SLIDE_UP, // This is the animation type and this is required
      builder: (context) => DashBoard())); // Your page
}
...
```

## PageRouteTransition class
```animationType, builder, curves``` are the parameters . ```animationType, builder``` are required

```dart
PageRouteTransition(
  animationType: AnimationType.SLIDE_UP, // takes an animation type enum
  builder: (context) => DashBoard(), // Takes a widget
  curves: Curves.easeInOut, // Optional curve
);
```

## Animation type
```AnimationType``` is exposed from the ```route_transitions.dart``` file itself . It is required and defines which animation to perform .

### Slide from right
In order to slide from right use this
```dart
PageRouteTransition(
  animationType: AnimationType.SLIDE_RIGHT,
  builder: (context) => DashBoard(),
);
```

### Slide from left
In order to slide from left use this
```dart
PageRouteTransition(
  animationType: AnimationType.SLIDE_LEFT,
  builder: (context) => DashBoard(),
);
```

### Slide from up
In order to slide from up use this
```dart
PageRouteTransition(
  animationType: AnimationType.SLIDE_UP,
  builder: (context) => DashBoard(),
);
```

### Slide from down
In order to slide from down use this
```dart
PageRouteTransition(
  animationType: AnimationType.SLIDE_DOWN,
  builder: (context) => DashBoard(),
);
```

### Fade animation
In order to fade , use this
```dart
PageRouteTransition(
  animationType: AnimationType.FADE,
  builder: (context) => DashBoard(),
);
```

### Scale animation
In order to scale , use this
```dart
PageRouteTransition(
  animationType: AnimationType.SCALE,
  builder: (context) => DashBoard(),
);
```

# Full example
```dart
import 'package:flutter/material.dart';
import 'package:route_transitions/route_transitions.dart';

void main() => runApp(MyApp());

const TextStyle style =
    TextStyle(fontFamily: "Poppins", fontSize: 22, color: Colors.black);

class MyApp extends StatelessWidget {
  @override
  Widget build(BuildContext context) {
    return MaterialApp(
      title: 'Flutter Demo',
      theme: ThemeData(
        primarySwatch: Colors.blue,
      ),
      home: Home(),
      debugShowCheckedModeBanner: false,
    );
  }
}

class Home extends StatefulWidget {
  Home({Key key}) : super(key: key);

  @override
  _HomeState createState() => _HomeState();
}

class _HomeState extends State<Home> {
  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.white,
      appBar: AppBar(
        backgroundColor: Colors.white,
        elevation: 8.0,
        title: Text(
          "Route animations",
          style: style,
        ),
        brightness: Brightness.light,
      ),
      body: Container(
        margin: EdgeInsets.symmetric(horizontal: 50),
        child: Column(
          mainAxisAlignment: MainAxisAlignment.center,
          crossAxisAlignment: CrossAxisAlignment.center,
          children: <Widget>[
            RaisedButton(
              elevation: 0.0,
              color: Colors.black,
              child: Center(
                child: Text(
                  "Slide from right",
                  style: style.copyWith(color: Colors.white),
                ),
              ),
              onPressed: () {
                Navigator.of(context).push(PageRouteTransition(
                    animationType: AnimationType.SLIDE_RIGHT,
                    builder: (context) => DashBoard()));
              },
            ),
            RaisedButton(
              elevation: 0.0,
              color: Colors.black,
              child: Center(
                child: Text(
                  "Slide from left",
                  style: style.copyWith(color: Colors.white),
                ),
              ),
              onPressed: () {
                Navigator.of(context).push(PageRouteTransition(
                    animationType: AnimationType.SLIDE_LEFT,
                    builder: (context) => DashBoard()));
              },
            ),
            RaisedButton(
              elevation: 0.0,
              color: Colors.black,
              child: Center(
                child: Text(
                  "Slide from up",
                  style: style.copyWith(color: Colors.white),
                ),
              ),
              onPressed: () {
                Navigator.of(context).push(PageRouteTransition(
                    animationType: AnimationType.SLIDE_UP,
                    builder: (context) => DashBoard()));
              },
            ),
            RaisedButton(
              elevation: 0.0,
              color: Colors.black,
              child: Center(
                child: Text(
                  "Slide from down",
                  style: style.copyWith(color: Colors.white),
                ),
              ),
              onPressed: () {
                Navigator.of(context).push(PageRouteTransition(
                    animationType: AnimationType.SLIDE_DOWN,
                    builder: (context) => DashBoard()));
              },
            ),
            RaisedButton(
              elevation: 0.0,
              color: Colors.black,
              child: Center(
                child: Text(
                  "Fade",
                  style: style.copyWith(color: Colors.white),
                ),
              ),
              onPressed: () {
                Navigator.of(context).push(PageRouteTransition(
                    animationType: AnimationType.FADE,
                    builder: (context) => DashBoard()));
              },
            ),
            RaisedButton(
              elevation: 0.0,
              color: Colors.black,
              child: Center(
                child: Text(
                  "Scale",
                  style: style.copyWith(color: Colors.white),
                ),
              ),
              onPressed: () {
                Navigator.of(context).push(PageRouteTransition(
                    animationType: AnimationType.SACLE,
                    builder: (context) => DashBoard()));
              },
            ),
          ],
        ),
      ),
    );
  }
}

class DashBoard extends StatelessWidget {
  const DashBoard({Key key}) : super(key: key);

  @override
  Widget build(BuildContext context) {
    return Scaffold(
      backgroundColor: Colors.white,
      appBar: AppBar(
        brightness: Brightness.light,
        title: Text(
          "Dashboard",
          style: style,
        ),
        backgroundColor: Colors.white,
        elevation: 8.0,
        leading: IconButton(
          icon: Icon(
            Icons.chevron_left,
            color: Colors.black,
          ),
          onPressed: () {
            Navigator.of(context).pop();
          },
        ),
      ),
      body: Center(
        child: Text(
          "Dashboard",
          style: style,
        ),
      ),
    );
  }
}

```
