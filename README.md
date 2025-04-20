# Sanskriti - SwiftUI Implementation

## Functional Requirements Implemented

### Image Carousel (`BannerView`)
- Built using SwiftUI’s `TabView` with `.tabViewStyle(.page)` for swipeable image pages.
- Updates the list content whenever the user swipes to a new image.
- Supports dynamic number of images (local or remote).

### List View (`FrequencySummaryView`)
- Scrollable vertical list built using SwiftUI’s `List` and `ScrollView`.
- Full-page scroll behavior for smooth navigation experience.
- List items update automatically based on selected banner image.

### Search Functionality (`SearchBarView`)
- Custom search bar view created using SwiftUI and pinned to top on scroll.
- As the user types, list items are filtered in real time.

### Floating Action Button (FAB)
- Positioned above the content using SwiftUI overlay and alignment techniques.
- Tapping FAB opens a custom bottom sheet displaying:
  - Total number of list items for current image page.
  - Top 3 most frequently occurring characters across list values.
    - Example:  
      Input: `["apple", "banana", "orange", "blueberry"]`  
      Output:
      - `a = 5`  
      - `e = 4`  
      - `r = 3`

## Architecture and Structure

### MVVM Architecture
- Structured under `Feature/HomeView`:
  - `Model`: `HomeUIModel`
  - `View`: `HomeView`
  - `ViewModel`: `HomeViewModel`
- Splash screen is also created under `SplashView`.

### Reusable SwiftUI Components
- Located in `Components`:
  - `BannerView`
  - `FrequencySummaryView`
  - `SearchBarView`
  - `ImageDetailsView`

### Core and Utility Layers
- Utility extensions inside `Core/Utilities/Extensions`:
  - `Array+Extension`
  - `Color+Extension`
- JSON loading handled via `Managers/JSONLoader`.
- `MediaGroup` model used to map local/remote JSON data.
