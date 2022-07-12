# Storybook accessibility test automation

This repository showcases accessibility test automation with Storybook Test Runner, Jest, Axe, and GitHub Actions, following the tutorial [Automate accessibility tests with Storybook](https://storybook.js.org/blog/automate-accessibility-tests-with-storybook/) from [Varun Vachhar](https://github.com/winkerVSbecks).

Additional documentation used to build this example:

- https://storybook.js.org/docs/react/writing-tests/test-runner
- https://storybook.js.org/docs/react/writing-tests/accessibility-testing
- https://www.chromatic.com/docs/ci
- https://www.chromatic.com/docs/github-actions

---

This Storybook is deployed on Chromatic: https://main--62cc72dcab307d1666bba837.chromatic.com

## What happens when an accessibility regression is introduced?

[Example pull request](https://github.com/kaelig/storybook-test-a11y-ci/pull/1):

### Storybook deploy

When you open a pull request or push a new commit, Storybook is automatically deployed to Chromatic ([view deploy for the example PR](https://62cc72dcab307d1666bba837-dbwxldbdui.chromatic.com/?path=/story/example-button--primary)), which shows the violation in the Accessibility panel (thanks to[`@storybook/addon-a11y`](https://storybook.js.org/addons/@storybook/addon-a11y)).

[![](https://user-images.githubusercontent.com/85783/178398250-23e96987-bea8-474b-82dd-7695dc4ba5af.png)](https://62cc72dcab307d1666bba837-dbwxldbdui.chromatic.com/?path=/story/example-button--primary)

### CI failure

When you open a pull request to this repository, it starts Storybook and runs accessibility tests on all stories. If a violation was found, the PR check fails:

[![](https://user-images.githubusercontent.com/85783/178397549-35cb0918-c140-4fe5-b4af-af28623fa49b.png)](https://github.com/kaelig/storybook-test-a11y-ci/pull/1)

```
[TEST] Test Suites: 3 failed, 3 total
[TEST] Tests:       3 failed, 5 passed, 8 total
[TEST] Snapshots:   0 total
[TEST] Time:        4.852 s
```

[Browse full test output log](https://github.com/kaelig/storybook-test-a11y-ci/runs/7292697893?check_suite_focus=true#step:7:1)
