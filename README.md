# injectpromise

A minimalistic package to insert a promise instead of using a callback.

### Usage

```

class SomeClass {

    constructor() {
        this.injectPromise = require('injectpromise')(this);
    }

    async getCurrent(callback = false) {

        if (!callback)
            return this.injectPromise(this.getCurrent);

        return callSomething
            .then(result => {
            callback(null, result);
        }).catch(err => callback(err));
    }

}

module.exports = SomeClass


``` 
