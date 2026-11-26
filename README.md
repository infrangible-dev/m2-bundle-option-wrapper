# Infrangible Bundle Option Wrapper

Adds an element around every option of a bundle product on the product page, so that themes and other modules can find
and style single options. The element has the ID `bundle-option-<option ID>`, the attribute `data-option-id` and these
CSS classes:

- `field-wrapper`
- `field-wrapper-<type>`, for example `field-wrapper-select` or `field-wrapper-checkbox`
- `field-wrapper-<title>`: the title of the option in lower case, with spaces replaced by underscores and an underscore
  before upper case letters, for example `field-wrapper-gift__wrap` for "Gift Wrap"

The options are separated by a line, like the custom options of
[Infrangible Catalog Product Option Wrapper](https://www.infrangible.dev/modules/catalog-product-option-wrapper).

## Requirements

- Magento Open Source or Adobe Commerce 2.4.6 or newer
- PHP 8.1 or newer

## Installation

```bash
composer require infrangible/m2-bundle-option-wrapper
bin/magento module:enable Infrangible_BundleOptionWrapper
bin/magento setup:upgrade
```

In production mode, also run `bin/magento setup:di:compile` and `bin/magento setup:static-content:deploy`.

## Usage in other modules

Other lists of bundle options can use the same wrapper: add a block of the class
`Infrangible\BundleOptionWrapper\Catalog\Product\View\Type\Bundle\Option` with the template
`Infrangible_BundleOptionWrapper::catalog/product/view/type/bundle/options/option.phtml` as child `bundle_option_wrapper`
of the block that renders the options, and wrap the HTML of each option with
`Infrangible\BundleOptionWrapper\Helper\Data::renderWrapper($block, $bundleOption, $bundleOptionHtml)`.

## License

Infrangible Bundle Option Wrapper is licensed under the MIT License - see the LICENSE file for details.
