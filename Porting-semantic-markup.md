Create a table mapping the old DOM to the new DOM using Emmet

Cross reference all class names and attributes in the JavaScript source using Firefox

Replace closures with global functions using JSLint

Create a new sample page in JSFiddle

Create filters to replace directives

## Directive Mapping Table
1. Logo Link

1a.
`<a ng-href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio" class="logo" tabindex="01" href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio">Select to open E*Trade Adaptive Portfolio home</a>`

1b.
`<a href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio | siteFilter" class="logo" tabindex="01" href="https://us.etrade.com/what-we-offer/our-accounts/adaptive-portfolio | siteFilter">Select to open E*Trade Adaptive Portfolio home</a>`

2. Progress Bar

2a.
    <div class="steps"><p class="step-indicator"><span ng-hide="questionId < 1 || questionId >= 9 " class="ng-binding" aria-hidden="false">Question 1/8</span> <span ng-show="questionId > 9" aria-label="Questionnaire" aria-hidden="true" class="ng-hide">Questionnaire</span></p><div ng-class="{active : isActive(1)}" class="active"></div><div ng-class="{active : isActive(2)}"></div><div ng-class="{active : isActive(3)}"></div><div ng-class="{active : isActive(4)}"></div><div ng-class="{active : isActive(5)}"></div><div ng-class="{active : isActive(6)}"></div><div ng-class="{active : isActive(7)}"></div><div ng-class="{active : isActive(8)}"></div><div class="major" ng-class="{active: isActive('result')}"><span>Result</span></div><div class="major" ng-class="{active: isActive('conversion')}"><span alt="Open an Account" class="ng-binding">Open an Account</span></div><div class="major" ng-class="{active: isFund()}"><span>Fund</span></div></div>`

2b.
    <div class="progress progress-segmented">`
	`<div class="progress-segment active">`
		`<span class="progress-label">Account Selection</span>	</div>`
	`<div class="progress-segment active">`
		`<span class="progress-label">Personal Information</span>`
	`</div>`
	`<div class="progress-segment">`
		`<span class="progress-label">Verify Identity</span>`
	`</div>`
	`<div class="progress-segment">`
		`<span class="progress-label">Investment Profile</span>`
	`</div>`
	`<div class="progress-segment">`
		`<span class="progress-label">Account Setup</span>`
	</div>
    </div>
## Container Markup Mapping Table
`div.partial-responsive => div.prospect|customer|android| `

`div#etContainer => container `

`nav-wrapper => div.row + div.col-xs-12 + header`

`div#questionTop => form`

`div.page-wrapper => div.row + div.col-xs-12 col-sm-12 col-md-6 col-md-offset-3`