# Changelog

## 2.0.1

### Changed

- Supports PHP 8.1 again, like Magento 2.4.6: the Adobe Commerce Marketplace requires modules to allow every PHP
  version of the Magento versions they support.

## 2.0.0

### Security

- The wrapper of bundle options added the type and title of the option to the HTML attributes without escaping. They
  are escaped now.

### Breaking changes

- Requires Magento 2.4.6 or newer and PHP 8.2 or newer. Magento 2.2 to 2.4.5 and PHP 7.1 to 8.1 are no longer
  supported; use version 1.x for these.
- Requires `infrangible/m2-foundation` 3.0, `fewedev/base` 2.4 and `magento/module-bundle`.
- The wrapper block `Catalog\Product\View\Type\Bundle\Option` gets the additional constructor argument `Variables`.
- All class properties, parameters and return values have native types. The plugin uses constructor property
  promotion.
- `Option::getBundleOption()` throws a `LogicException` if the block has no bundle option.

### Changed

- The wrapper has no class for an empty title of the option (`field-wrapper-`) any more.
- The CSS classes of the wrapper come from `Option::getWrapperClasses()`, the ID from `Option::getBundleOptionId()`.
- The module is loaded after Magento's bundle module.
- Checks with PHPStan level 9, the Magento coding standard and unit tests on every push.

### Added

- Unit tests.
- README with the CSS classes and the usage in other modules.
