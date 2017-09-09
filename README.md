# ionic-protractor-mock
Request mock plugin for Ionic.

A simple example of usage:

```ts
import {browser, $} from 'protractor';
import {MockService} from 'ionic-protractor-mock';

describe('the backend', () => {
  it('should reply with code 418', () => {
    MockService.setup(browser);
    MockService.addMock('mock1', {
      path: '/api/teapot',
      response: {status: 418, data: "I'm a teapot"},
    });

    $('button').click();
    expect($('div').getText()).toEqual("I'm a teapot");
  });
});
```
