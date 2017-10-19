Create a table mapping the old DOM to the new DOM using Emmet

Copy code from the new baseline site to new files

Cross reference all class names and attributes in the JavaScript source using Firefox

Create new templates to replace old templates

Find all references to the existing templates using a recursive search for the html file names through the project
Replace old file references with new file references

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

    <div class="steps">
        <p class="step-indicator"><span ng-hide="questionId &lt; 1 || questionId &gt;= 9" class="ng-binding" aria-hidden=
        "false">Question 1/8</span> <span ng-show="questionId &gt; 9" aria-label="Questionnaire" aria-hidden="true" class=
        "ng-hide">Questionnaire</span></p>

        <div ng-class="{active : isActive(1)}" class="active"></div>

        <div ng-class="{active : isActive(2)}"></div>

        <div ng-class="{active : isActive(3)}"></div>

        <div ng-class="{active : isActive(4)}"></div>

        <div ng-class="{active : isActive(5)}"></div>

        <div ng-class="{active : isActive(6)}"></div>

        <div ng-class="{active : isActive(7)}"></div>

        <div ng-class="{active : isActive(8)}"></div>

        <div class="major" ng-class="{active: isActive('result')}">
            <span>Result</span>
        </div>

        <div class="major" ng-class="{active: isActive('conversion')}">
            <span alt="Open an Account" class="ng-binding">Open an Account</span>
        </div>

        <div class="major" ng-class="{active: isFund()}">
            <span>Fund</span>
        </div>
    </div>

2b.

    <div class="progress progress-segmented">
	<div class="progress-segment active">
		<span class="progress-label">Account Selection</span>
        </div>
	<div class="progress-segment active">
		<span class="progress-label">Personal Information</span>
	</div>
	<div class="progress-segment">
		<span class="progress-label">Verify Identity</span>
	</div>
	<div class="progress-segment">
		<span class="progress-label">Investment Profile</span>
	</div>
	<div class="progress-segment">
		<span class="progress-label">Account Setup</span>
	</div>
    </div>

3. Contact Section

3a.

        <div class="contact">
            <a href="/frequently-asked-questions#tab_t1" target="_blank" class=
            "et-icon-question before faq-icon" aria-label=
            "Select to open Frequently Asked Questions page" tabindex=
            "01"><span>FAQ</span></a> <a href="tel:866-484-3658" class="icon-call" alt=
            "Call us 866-484-3658" tabindex="01"><span>Call Us 866-484-3658</span></a>
            <button role="link" class="icon-chat no-style" ng-click="openChat()"
            aria-label="Chat online" tabindex="01"><span>Chat Online</span></button>
        </div>

3b.

        <div class="contact">
            <a href="/frequently-asked-questions#tab_t1" id="faq-link" class=
            "et-icon-question before faq-icon" aria-label=
            "Select to open Frequently Asked Questions page" tabindex=
            "01"><span>FAQ</span></a> <a href="tel:866-484-3658" class="icon-call" alt=
            "Call us 866-484-3658" tabindex="01"><span>Call Us 866-484-3658</span></a>
            <button role="link" class="icon-chat no-style" ng-click="openChat()"
            aria-label="Chat online" tabindex="01"><span>Chat Online</span></button>
        </div>

4. Spinner

4a.

    <div class="cards clearfix calc ng-scope">
        <div class="calc-wrapper clearfix">
            <div class="hex">
                <div class="triangle-wrapper">
                    <div class="triangle t1"></div>

                    <div class="triangle t2"></div>

                    <div class="triangle t3"></div>

                    <div class="triangle t4"></div>

                    <div class="triangle t5"></div>

                    <div class="triangle t6"></div>
                </div>
            </div>

            <h1>Calculating Your <span>Risk Profile</span></h1>
        </div>
    </div>

4b.

    <div class="spinner">
      <svg class="circular" viewBox="25 25 50 50">
        <circle class="background" cx="50" cy="50" r="20" fill="none" stroke-width="2" stroke-miterlimit="10"></circle>
        <circle class="path" cx="50" cy="50" r="20" fill="none" stroke-width="2" stroke-miterlimit="10"></circle>
      </svg>
    </div>

5. Question 1 (RTQ and KYC)

5a. 
 
    <div ng-class="config.questionClass[1].classArray[0]" role="radio" tabindex="20"
    ng-click="setAnswer(1,0)" aria-checked="false" aria-label=
    "Click to select less than 2 years option" class="option">
        <div class="circ">
            <p>&lt; 2<span>Less than</span><span>2 years</span></p>
        </div>

        <p aria-hidden="true" role="presentation">Less than <span>2 years</span></p>
    </div>

5b.

    <div class="et-select-wrapper voffset3"><!-- ngInclude: 'account_list' | filterAccountsList:config.acctData.CIOEligibleAccounts.accounts -->
      <select name="account_list" ng-model="config.conversionData.selectedAcct" ng-init="config.conversionData.selectedAcct = config.conversionData.selectedAcct || config.acctData.CIOEligibleAccounts.accounts[0].acctNo" id="account_list" ng-include="'account_list' | filterAccountsList:config.acctData.CIOEligibleAccounts.accounts" ng-change="config.conversionData.changeAcct($event)" class="ng-pristine ng-valid ng-scope ng-touched" tabindex="0" aria-invalid="false"><option aria-label="Click to select account INDIVIDUAL" name="INDIVIDUAL" value="GEN" class="ng-scope">INDIVIDUAL</option><option aria-label="Click to select account JN" name="JN" value="GEN3" class="ng-scope">JN</option><option aria-label="Click to select account KD" name="KD" value="GEN4" class="ng-scope">KD</option></select></div>

5c.

    <label for="select1">Select input field</label>

    <div class="select-wrapper">
        <select class="form-control" name="select1">
            <option>
                Lorem ipsum
            </option>

            <option>
                Dolor
            </option>

            <option>
                Sit amet
            </option>
        </select>
    </div>

5c.

6. Tax-Sensitive Radio Buttons

6a.

    <div ng-if="config.state === 'conversion'" class="ng-scope">
        <p class="voffset4"><input type="radio" class="form-control tax-selection" name=
        "reduce_taxes" id="reduce_taxes" aria-label="Click to select Yes." value="1"
        ng-click="config.questionData.kycProfile.questionAnswers['6'].answerId = '1'"
        tabindex="0"><label id="sensitive_help" for="reduce_taxes">Yes. Provide me with a
        tax-sensitive portfolio that helps reduce the impact of taxes on ETF
        returns.</label></p>

        <p class="voffset4"><input type="radio" class="form-control tax-selection" name=
        "reduce_taxes" id="normal_taxes" aria-label="Click to select No." value="2"
        ng-click="config.questionData.kycProfile.questionAnswers['6'].answerId = '2'"
        tabindex="0"><label id="non-sensitive_help" for="normal_taxes">No. I do not want
        a tax-sensitive portfolio.</label></p>
    </div>

6b.

    <div class="col-xs-12 col-sm-6">
              <div class="radio">
                <input type="radio" name="radioA" id="radio1-not-selected" value="option0">
                <label for="radio1-not-selected">Radio button not selected</label>
              </div>
              <div class="radio">
                <input type="radio" name="radioA" id="radio1-selected" value="option1" checked="">
                <label for="radio1-selected">Radio button pre-selected</label>
              </div>
    </div>

7. Checkboxes

7a.

    <input id="i_accept" class="form-control ng-pristine ng-untouched ng-valid" type="checkbox" ng-model="config.conversionData.agreementChecked" ng-disabled="config.conversionData.submitted" ng-click="config.conversionData.agreementStatus()" aria-label="Click to select" aria-describedby="accept_text" aria-controls="approve_sell" aria-required="true" aria-checked="" tabindex="0" aria-invalid="false">

7b.

    <div class="checkbox">
      <input type="checkbox" name="checkbox1" value="checkbox1-A">
      <label for="checkbox1-A">Checkbox not selected</label>
    </div>

8. Spinner

8a.

    <div class="cards clearfix calc ng-scope">
      <div class="calc-wrapper clearfix">
        <div class="hex">
          <div class="triangle-wrapper">
           <div class="triangle t1"></div>
           <div class="triangle t2"></div>
           <div class="triangle t3"></div>
           <div class="triangle t4"></div>
           <div class="triangle t5"></div>
           <div class="triangle t6"></div>
          </div>
        </div>
        <h1>Calculating Your <span>Risk Profile</span></h1>
      </div>
    </div>

8b.

    <div class="spinner">
      <svg class="circular" viewBox="25 25 50 50">
        <circle class="background" cx="50" cy="50" r="20" fill="none" stroke-width="2" stroke-miterlimit="10"></circle>
        <circle class="path" cx="50" cy="50" r="20" fill="none" stroke-width="2" stroke-miterlimit="10"></circle>
      </svg>
    </div>

9. Error

9a.

    <div class="result-err-box ng-scope" ng-if="showerr &amp;&amp; type==='result'">
      <div class="panel-warning panel clearfix">
        <div class="col-xs-2 col-sm-1 col-lg-1">
          <span class="et-icon-exclamation-tri warning-size-small" aria-label="Warning"></span>
        </div>
        <div class="col-xs-10 col-sm-11 col-lg-11">
          <p class="voffset ng-binding" ng-bind="message">
            Due to chart display issue, we were unable to proceed. Please re-start the application
          </p>
        </div>
      </div>
    </div>

9b.

    <div class="universal-message universal-message-danger" role="alert">
      <div class="universal-message-content">
        <h4 class="universal-message-heading">Action Required</h4>
        <p>
        We would like to ensure that we have the most up-to-date records for your account. 
        Please take a moment to confirm or update your contact information. 
        <a href="">Click here</a> to review.
        </p>
      </div>
    </div>

## Container Markup Mapping Table
`div.partial-responsive => div.prospect|customer|android| `

`div#etContainer => container `

`nav-wrapper => div.row + div.col-xs-12 + header`

`div#questionTop => form`

`div.page-wrapper => div.row + div.col-xs-12 col-sm-12 col-md-6 col-md-offset-3`


http://demo.bootstraptor.com/blocks.html
https://webdesign.tutsplus.com/tutorials/bootstrap-3-succinctly-migrating-from-version-2-to-version-3--cms-23132
http://upgrade-bootstrap.bootply.com
https://webmuch.com/upgrade-bootstrap-2-twitter-bootstrap3-build/