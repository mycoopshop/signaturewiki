## State Machine Design
Use a map with string equality checks to implement a simple state machine:

    setLandingPage(numberOfAccounts, numberOfPlans, oneAccount){
    const pageMap = {
    'true,true,true': {landingPage:'foo'},
    'true,true,false': {landingPage:'foo'},
    'true,false,true': {landingPage: 'bar'},
    'true,false,false': {landingPage: 'baz'},
    'false,false,false': {landingPage: 'baz'},
    'false,true,false': {landingPage: 'baz'}
    };

    const key = String().concat(numberOfAccounts,',',numberOfPlans);

    let result = pageMap(key);

    return pageMap[numberOfAccounts, numberOfPlans];
    }

## References

* https://www.codeproject.com/Articles/1275479/State-Machine-Design-in-C