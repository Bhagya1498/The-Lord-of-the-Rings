# The Lord of the Rings Movie App 🎬🧙‍♂️

This Android application displays a list of **The Lord of the Rings** movies, characters, and their quotes. It uses a clean architecture setup with MVVM, Retrofit for network calls, and Kotlin Coroutines for async operations. The app handles data responses using a `Resource` sealed class to represent success, loading, and error states.

---

## 🚀 Features

- View a list of **movies**
- View **paginated characters** for each movie
- View detailed **character info** including **quotes**
- Clean error & loading state handling using a `Resource` sealed class

---

## 🛠️ Tech Stack

- Kotlin
- MVVM Architecture
- Retrofit + Gson
- Kotlin Coroutines + Flow
- LiveData or StateFlow (depending on implementation)
- Jetpack ViewModel, Navigation Component
- Hilt (optional for DI)

---

## 📁 Project Architecture
<pre>
com.example.myapplication
├── core/                             # Shared utilities and configuration
│   ├── common/                       # Base classes, constants
│   ├── di/                           # Dependency injection modules (Hilt)
│   ├── network/                      # Retrofit setup, interceptors, response handling
│   ├── navigation/                   # Navigation graphs or destinations
│   └── utils/                        # Helper classes and utilities
│
├── features/
│   ├── movie/
│   │   ├── presentation/             # UI layer - ViewModel, Fragment, Adapter
│   │   ├── data/
│   │       ├── local/                # Local data sources (Room DB, cache)
│   │       ├── remote/               # Remote data sources (API calls using Retrofit)
│   │       └── repository/           # Implementation of repository interface                  
│   │
│   ├── character/                    # Same structure as movie
│   │   ├── presentation/
│   │   ├── data/
│   │      ├── local/
│   │      ├── remote/
│   │      └── repository/
│   │
│   └── quote/                        # Same structure as movie
│       ├── presentation/
│       ├── data/
│           ├── local/
│           ├── remote/
│           └── repository/       
│
├── MainActivity.kt
├── MyApplication.kt
│
├── test/                             # Unit tests
    ├── FakeApiService.kt
    ├── MovieRepositoryTest.kt
    └── ExampleUnitTest.kt
</pre>


## 🧪 Important Components

- `MovieRepository`, `CharacterRepository`, `QuoteRepository`: Use the `Resource<T>` sealed class to wrap API responses.
- `Resource.kt`: A sealed class with `Success<T>`, `Error(String)`, and `Loading` states.
- `CharacterListViewModel`, `CharacterDetailViewModel`: Fetch characters and quotes with proper state handling.
- `MovieScreen`, `CharacterScnree`: Developed in Jetpack Compose for UI.



