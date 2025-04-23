# Compose forms
watch this preview
[![Compose Forms](https://img.youtube.com/vi/In7yu9AO8vg/1.jpg)](https://www.youtube.com/watch?v=In7yu9AO8vg)


Compose Forms is a Kotlin-based Android application that demonstrates the implementation of login, sign-up, and "About" screens using Jetpack Compose. The app uses modern Compose UI principles, animations, and design patterns to create a seamless user experience.

## Features

- **Login Screen**: A simple login form with email and password fields, complete with animations for visibility transitions.
- **Sign-Up Screen**: A sign-up form with fields for username, email, password, and password confirmation, also featuring smooth animations.
- **About Screen**: A screen providing details about the app and its author. Includes a bottom sheet for extended information.
- **Pager Navigation**: Swipeable navigation between the "About," "Login," and "Sign-Up" screens using a horizontal pager.
- **Responsive UI**: Built using Material Design 3 components for a modern and user-friendly interface.
- **Animations**: Includes fade-in, fade-out, and slide-in/slide-out animations for dynamic UI interactions.

## Screens Overview

### 1. Login Screen
- **Fields**: Email and Password.
- **Features**:
  - Animated visibility toggle for the login form.
  - Password masking using `PasswordVisualTransformation`.
  - Validation-ready design.

### 2. Sign-Up Screen
- **Fields**: Username, Email, Password, and Confirm Password.
- **Features**:
  - Animated visibility toggle for the sign-up form.
  - Password masking for secure input.
  - UI designed for a clean and intuitive user experience.

### 3. About Screen
- **Details**:
  - Provides a brief description of the app and its author.
  - Includes a bottom sheet for extended content.
- **Features**:
  - Learn more button to expand the bottom sheet.
  - Text content styled for readability using Material Design typography.

### 4. Pager Navigation
- **Screens**:
  - "About," "Login," and "Sign-Up."
- **Features**:
  - Swipeable navigation using Jetpack Compose's `HorizontalPager`.
  - Smooth transitions between screens.

## Installation

1. Clone the repository:
   ```bash
   git clone https://github.com/zaid-kamil/Compose-Forms.git
   ```
2. Open the project in Android Studio.
3. Build and run the application on an Android emulator or physical device.

## Code Highlights

### MainActivity
The entry point of the app, setting up the Compose theme and a `Scaffold` with the PagerScreen.

```kotlin
class MainActivity : ComponentActivity() {
    override fun onCreate(savedInstanceState: Bundle?) {
        super.onCreate(savedInstanceState)
        enableEdgeToEdge()
        setContent {
            ComposeFormsTheme {
                Scaffold(modifier = Modifier.fillMaxSize()) { innerPadding ->
                    PagerScreen(modifier = Modifier.padding(innerPadding))
                }
            }
        }
    }
}
```

### PagerScreen
Handles swipeable navigation between the "About," "Login," and "Sign-Up" screens.

```kotlin
@Composable
fun PagerScreen(modifier: Modifier = Modifier) {
    val pagerState = rememberPagerState(initialPage = 0, pageCount = { 3 })
    Box(
        modifier = modifier.fillMaxSize(),
        contentAlignment = Alignment.Center
    ) {
        HorizontalPager(state = pagerState, modifier = Modifier.fillMaxSize()) {
            when (it) {
                0 -> AboutScreen(modifier)
                1 -> LogInScreen(modifier)
                2 -> SignUpScreen(modifier)
            }
        }
    }
}
```

## Contributing

Contributions are welcome! If you’d like to contribute:
1. Fork the repository.
2. Create a new branch for your feature or bug fix.
3. Submit a pull request with a detailed description of your changes.

## License

This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.
