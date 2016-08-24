# Ember.js Styleguide

This styleguide aims to suggest some style conventions to follow while writing your application.

Note: evaluate each suggestion and consider where it's right fit for you.

## JavaScript

### Use fat arrow to preserve `this`

Fat arrow automatically maintains a reference to the context when using `this` in a closure. 

```javascript
export default Ember.Route.extend({
  afterModel(model) {

    return this.get('ajax').request('verify', model)
      .catch((error) => {
        // this refers to the Route instance
        this.transtionTo('verification-failed', error);
      });
  }
  
});
```

## Object model

