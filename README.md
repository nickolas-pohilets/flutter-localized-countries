# flutter_localized_countries

For 122 languages
- Country code to name mappings.
- Locale code to name mappings.

This is a port of an npm package [localized-countries](https://github.com/marcbachmann/localized-countries) for [Flutter](https://flutter.io).

Data is taken from [https://github.com/umpirsky/country-list](https://github.com/umpirsky/country-list) and [https://github.com/umpirsky/locale-list](https://github.com/umpirsky/locale-list).

This package bundles required assets and provides custom [LocalizationsDelegates](https://docs.flutter.io/flutter/widgets/LocalizationsDelegate-class.html) for loading them.

## Usage

### Country names 
```$dart
import 'package:flutter_localized_countries/flutter_localized_countries.dart';

void main() {
  runApp(MaterialApp(
    localizationsDelegates: [
      CountryNamesLocalizationsDelegate(),
      // ... more localization delegates
      GlobalMaterialLocalizations.delegate,
      GlobalWidgetsLocalizations.delegate,
    ],
    ...
  );
  
  ...
  
  print(CountryNames.of(context).nameOf('NL')); // Netherlands;
}
```
### Locale names
```$dart
import 'package:flutter_localized_countries/flutter_localized_countries.dart';

void main() {
  runApp(MaterialApp(
    localizationsDelegates: [
      LocaleNamesLocalizationsDelegate(),
      // ... more localization delegates
      GlobalMaterialLocalizations.delegate,
      GlobalWidgetsLocalizations.delegate,
    ],
    ...
  );
  
  ...
  
  print(LocaleNames.of(context).nameOf('en_GB')); // English (United Kingdom)
}
```

## Known Bugs

* Sorting by name does not respect the locale, because Flutter does not provide any [API for string collation](https://github.com/flutter/flutter/issues/27549).
