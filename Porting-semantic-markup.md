Create a table mapping the old DOM to the new DOM using Emmet

Cross reference all class names and attributes in the JavaScript source using Firefox

Replace closures with global functions using JSLint

Create a new sample page in JSFiddle

Create filters to replace directives

## Directive Mapping Table
1. Logo Link
1a.
<a ng-href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio" class="logo" tabindex="01" href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio">Select to open E*Trade Adaptive Portfolio home</a>

1b.
<a href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio | siteFilter" class="logo" tabindex="01" href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio | siteFilter">Select to open E*Trade Adaptive Portfolio home</a>

## Container Markup Mapping Table
`div.partial-responsive => div.prospect|customer|android| `

`div#etContainer => container `

`nav-wrapper => div.row + div.col-xs-12 + header`

`div#questionTop => form`

`div.page-wrapper => div.row + div.col-xs-12 col-sm-12 col-md-6 col-md-offset-3`