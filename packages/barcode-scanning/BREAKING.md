# Breaking Changes

This is a comprehensive list of the breaking changes introduced in the major version releases of Capacitor ML Kit Barcode Scanning plugin.

## Versions

- [Version 7.x.x](#version-7xx)
- [Version 6.x.x](#version-6xx)
- [Version 5.x.x](#version-5xx)

## Version 7.x.x

### Minimum Deployment Target

On **iOS**, make sure to set the deployment target in your `ios/App/Podfile` to at least `15.5`:

```ruby
platform :ios, '15.5'
```

### Image Resolution

on **Android**, the image resolution used for barcode scanning has been increased to `1280x720` to improve the barcode scanning performance and be consistent with the iOS implementation. Previously, the resolution was `640x480`. You can change the resolution by setting the `resolution` option when calling the `startScan` method.

```typescript
import { BarcodeScanner, Resolution } from '@capacitor-mlkit/barcode-scanning';

const startScan = async () => {
  await BarcodeScanner.startScan({
    resolution: Resolution['640x480'],
  });
};
```

## Version 6.x.x

### Variables

- On Android, the `mlkitBarcodeScanningVersion` variable has been updated to `17.2.0`.
- On Android, the `playServicesCodeScannerVersion` variable has been updated to `16.1.0`.

## Version 5.x.x

### Capacitor 5

This plugin now supports Capacitor 5 only. Please run `npx cap sync` after updating this package.

If you want to use this plugin with Capacitor 4, please install version `0.0.3`:

```
npm i @capacitor-mlkit/barcode-scanning@0.0.3
```

### Corner Points

The calculation of the corner points has been improved. The coordinates are now multiplied by the pixel ratio of the device.
