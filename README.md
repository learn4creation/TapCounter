# Tap Counter (Android)

Counts table-tennis ball taps on a racket using the microphone.

## Build
1. Open the `TapCounter` folder in Android Studio (Koala or newer).
2. Let Gradle sync (Android Studio creates the Gradle wrapper automatically).
3. Connect a phone (USB debugging on) and press Run.

## Use
Press **PLAY**, allow microphone access, and tap. The big number is the tap count.
Press **STOP** to end, **Reset** to zero the counter.
If it misses taps, move the Sensitivity slider right; if it counts
talking/background noise, move it left.

## Detection (TapDetector.kt)
High-pass 2.5 kHz → 5.8 ms frame energy → compare with median background of
the last 0.4 s → count when energy is ~8× background and jumps sharply,
with a 70 ms lockout so a single tap isn't counted twice.
