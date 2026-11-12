# Mobile Standards (React Native / Expo)

## Lists and rendering
### Use virtualised lists for anything that can grow
**Rule:** Use `FlatList`, `SectionList`, or FlashList for lists. Don't `.map()` an unbounded array inside a `ScrollView`.
**Primary reason:** Rendering every row hurts memory and scroll performance.
**Does not apply when:** a short, fixed list (about 10 items or fewer).

### Keep list items cheap
**Rule:** Memoise row components, give a stable `keyExtractor`, and avoid creating new objects/functions per row where it triggers re-renders.
**Check:** profile with React DevTools / Flipper before and after.

## Navigation and screens
### Handle all screen states and lifecycle
**Rule:** Loading, empty, error, and offline states for each screen. Cancel in-flight requests when the screen unmounts or loses focus.

### Validate deep-link and push params
**Rule:** Treat deep-link and notification payloads as untrusted input. Parse with a schema and check the user is allowed to see the target.

## Layout and platform
### Respect safe areas and both platforms
**Rule:** Use safe-area insets, handle keyboard avoidance, and test on both iOS and Android. Use `Platform.select` only when behaviour truly differs.

### Support dark mode and dynamic type
**Rule:** Colours come from a theme that handles light and dark. Text scales with the system font size without clipping.

## Accessibility
### Label every interactive element
**Rule:** Set `accessibilityRole` and `accessibilityLabel` (or visible text). Touch targets are at least 44x44 pt (iOS) / 48x48 dp (Android). Check with VoiceOver and TalkBack.

## Storage and security
### Secrets in secure storage only
**Rule:** Store tokens in the Keychain/Keystore (e.g. `expo-secure-store`), not `AsyncStorage`. Anything with an `EXPO_PUBLIC_` prefix ships inside the app and is public; never put secrets there.
**Primary reason:** App bundles can be unpacked and AsyncStorage is unencrypted.

## Networking and offline
### Assume flaky networks
**Rule:** Set timeouts, retry idempotent requests with backoff, queue or clearly fail writes while offline, and show sync state.

## Performance and release
### Watch startup, bundle size, and JS thread work
**Rule:** Keep Hermes on, lazy-load heavy screens, move heavy work off the JS thread, and keep animations on the native driver (Reanimated).
### Release safely
**Rule:** Use staged rollouts. Over-the-air updates (EAS Update) may ship JS/asset changes only; native changes need a store build. Declare required permissions with a plain-language reason.
**Check:** a release checklist in the PR for store policy, permissions, and privacy labels.
