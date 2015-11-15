# How to stop hating your tests (@searls, @testdouble)

## Rule of Product
four variables and you multiply all possible values = you get upperbound
2 x 2 x 2 x 2 = 16 tests

**1 public function and 3 dependencies for a module**

## Test Anatomy
1. Sets stuff up (Given)
2. invokes a thing (When)
3. Verifies behavior (Then)

- Minimize each phase to 1 action
- jasmine-given/mocha-given
- AAA/GWT tests

## Accidentally Creative
- Consistent testing standards, always prefer consistency
- Tests data should be minimal and minimally meaningful


# Test isolation
Is the purpose of each test readily apparent?
http://is.gd/breaking_up

**The testing Pyramid**
Start with two test suites - each tackling one extreme
- one as integrated as possible, one as isolated as possible

# How realistic should tests be?
- realistic are slower
- take more time to write/change/debug
- higher cognitive load
- less integrated tests offer more design feedback and failures are easier to understand

# Test Double
a stunt double for tests - anything that stands in for your test: fake, stub, mock, spy (td.js, testdouble.js)
`npm install testdouble`
http://is.gd/discovery_testing

# Test feedback
Useless error messages add friction to workflow
**Judge assertion libraries on their message quality, not only their API**



**480 minutes in a workday**
**Profile productivity by measuring and optimizing your own feedback loops.**


## True negative vs. false negative
True negative: red means broken, fix the code
False negative: red means broken, fix the test

False negatives erode confidence in tests

### Top causes:
- Redundant coverage
- Slow tests
    - i.e. lots of integration tests

Track whether each failure is a true or false negative
