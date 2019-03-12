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

Use Array.from to generate states:

    const markup = Array.from({length: 5}, (v, i) => ({ spec: `HTML-${i}` }))

Use Map to generate functions for each state as an IDL:

    var bar = new Map()
    bar.set(Error.toString, function(){return 1}))
    bar.set(ReferenceError.toString, function(){return 2}))
    bar.set(SyntaxError.toString, function(){return 3}))
    bar.set(URIError.toString, function(){return 4}))

## References

* https://www.codeproject.com/Articles/1275479/State-Machine-Design-in-C

* http://wiki.c2.com/?AutomatedCodeGeneration

* http://ithare.com/ultra-fast-serialization-of-c-objects/