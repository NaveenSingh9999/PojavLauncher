# 🎨 LamLauncher UI Design System

## Color Palette

### Primary Colors
```xml
lam_primary:        #6C63FF  // Main brand color - Vibrant Purple
lam_primary_dark:   #5548E6  // Darker shade for depth
lam_primary_light:  #8B84FF  // Lighter shade for highlights
lam_accent:         #00D9FF  // Accent color - Bright Cyan
lam_accent_dark:    #00B8D9  // Darker cyan for contrast
```

### Background Colors (Dark Theme)
```xml
background_app:         #0F0F14  // Main app background - Deep dark
background_card:        #1A1A24  // Card/panel background
background_elevated:    #252532  // Elevated surfaces
background_overlay:     #2A2A38  // Overlays and dividers
background_status_bar:  #0A0A0F  // Status bar (darker)
background_bottom_bar:  #0F0F14  // Navigation bar
```

### Text Colors
```xml
primary_text:    #FFFFFF  // Main text - White
secondary_text:  #9FA2B4  // Secondary text - Light Gray
tertiary_text:   #6B6E82  // Tertiary text - Muted Gray
```

### Semantic Colors
```xml
success:  #00E676  // Green - Success states
warning:  #FFB300  // Amber - Warning states
error:    #FF5252  // Red - Error states
info:     #00D9FF  // Cyan - Info states
```

### Surface Colors
```xml
surface_high:    #2D2D3D  // Highest elevation
surface_medium:  #232330  // Medium elevation
surface_low:     #1A1A24  // Lowest elevation
```

### Control Colors
```xml
control_button_color:         #55FFFFFF  // Semi-transparent white
control_button_pressed_color: #886C63FF  // Primary with transparency
control_button_hover:         #666C63FF  // Hover state
```

---

## Typography System

### Font Family
- **Primary:** sans-serif (System default)
- **Fallback:** Roboto

### Font Sizes (Scalable)
- **Large Title:** 24sp
- **Title:** 20sp
- **Headline:** 18sp
- **Body:** 14sp
- **Caption:** 12sp (default)
- **Small:** 10sp

### Font Weights
- **Bold:** 700
- **Semi-Bold:** 600
- **Regular:** 400
- **Light:** 300

---

## Spacing System

### Base Unit: 4dp

```
Tiny:    4dp   (padding_tiny)
Small:   8dp   (padding_small)
Medium:  16dp  (padding_medium)
Large:   24dp  (padding_large)
XLarge:  32dp  (padding_xlarge)
XXLarge: 48dp  (padding_xxlarge)
```

---

## Components

### Buttons

#### Primary Button
- Background: `lam_primary`
- Text: `primary_text`
- Pressed: `lam_primary_dark`
- Corner radius: 8dp
- Min height: 48dp
- Padding: 16dp horizontal

#### Secondary Button
- Background: `background_elevated`
- Text: `secondary_text`
- Border: 1dp `lam_primary`
- Corner radius: 8dp

#### Ghost Button
- Background: transparent
- Text: `lam_primary`
- No border
- Ripple: `control_button_hover`

### Cards

#### Standard Card
- Background: `background_card`
- Corner radius: 12dp
- Elevation: 4dp
- Padding: 16dp
- Margin: 8dp

#### Elevated Card
- Background: `background_elevated`
- Corner radius: 12dp
- Elevation: 8dp
- Padding: 16dp

### Input Fields

#### Text Input
- Background: `background_elevated`
- Border: 1dp `divider`
- Corner radius: 8dp
- Padding: 12dp
- Focus border: 2dp `lam_primary`

### Dialogs

#### Standard Dialog
- Background: `background_card`
- Corner radius: 16dp
- Padding: 24dp
- Max width: 320dp

---

## Animations

### Duration
- **Fast:** 150ms
- **Normal:** 250ms
- **Slow:** 400ms

### Easing
- **Standard:** cubic-bezier(0.4, 0.0, 0.2, 1)
- **Decelerate:** cubic-bezier(0.0, 0.0, 0.2, 1)
- **Accelerate:** cubic-bezier(0.4, 0.0, 1, 1)

### Transitions
- Fade in/out
- Slide up/down
- Scale (for emphasis)

---

## Icons & Graphics

### Icon Sizes
- **Small:** 16dp
- **Medium:** 24dp (standard)
- **Large:** 32dp
- **XLarge:** 48dp

### Icon Colors
- **Primary:** `primary_text`
- **Secondary:** `secondary_text`
- **Accent:** `lam_accent`

---

## Accessibility

### Contrast Ratios
- **Normal text:** 4.5:1 minimum
- **Large text:** 3:1 minimum
- **Interactive elements:** 3:1 minimum

### Touch Targets
- **Minimum size:** 48dp × 48dp
- **Recommended:** 56dp × 56dp

### Focus Indicators
- **Outline:** 2dp `lam_primary`
- **Offset:** 2dp

---

## Responsive Design

### Breakpoints
- **Compact:** < 600dp (phones)
- **Medium:** 600dp - 840dp (tablets)
- **Expanded:** > 840dp (large tablets)

### Layout Adaptations
- Portrait: Single column
- Landscape: Optimized for gameplay

---

## Implementation Examples

### XML Button Style
```xml
<Button
    android:layout_width="match_parent"
    android:layout_height="48dp"
    android:background="@drawable/button_primary"
    android:textColor="@color/primary_text"
    android:textSize="14sp"
    android:fontFamily="sans-serif"
    android:paddingHorizontal="16dp"
    android:elevation="2dp" />
```

### XML Card Style
```xml
<androidx.cardview.widget.CardView
    android:layout_width="match_parent"
    android:layout_height="wrap_content"
    android:layout_margin="8dp"
    app:cardBackgroundColor="@color/background_card"
    app:cardCornerRadius="12dp"
    app:cardElevation="4dp">
    <!-- Card content -->
</androidx.cardview.widget.CardView>
```

---

## Best Practices

### Color Usage
1. Use primary colors sparingly for emphasis
2. Maintain consistent backgrounds
3. Ensure sufficient contrast
4. Test in both light and dark environments

### Typography
1. Maintain clear hierarchy
2. Use appropriate sizes for content
3. Ensure readability at all sizes
4. Consistent line heights

### Spacing
1. Use the spacing system consistently
2. Maintain breathing room
3. Group related elements
4. Align to the 4dp grid

### Animation
1. Keep animations subtle
2. Use appropriate durations
3. Don't overanimate
4. Provide feedback for actions

---

## Tools & Resources

### Design Tools
- Figma (recommended)
- Adobe XD
- Sketch

### Testing
- Device emulators
- Real device testing
- Accessibility scanner

### References
- [Material Design 3](https://m3.material.io/)
- [Android Design Guidelines](https://developer.android.com/design)

---

**LamLauncher Design System v1.0**
*Last updated: 2025*
