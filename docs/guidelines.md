# Set of Guidelines

In this page will be documented the overall guidelines and philosophy of multiple facets of the project, either some high level approach or delving into specifics.

## Work Organisation

Development will be done by setting up iterations, which consist of a set of epics / stories that will be handled in one bundle before definig the next. This is similar to the common sprint, except that there is no time constraint.

For the specifics :

- An issue needs to be as descriptive as possible to avoid any back and forth during development due to lack of information / unclear specifications.
- A story is an issue that will be handled in an epic. All issues are not necessarily stories though.
- An epic is a set of stories grouped by context. For example, all stories related to the card search feature(s) are in the same `Search` epic.
- Some stories (eg: bug regression discovered while working on an unrelated epic) might be too niche to have an epic. This should not be the norm though.
- Epics are planned in iterations. Ideally we should avoid having epics that span multiple iterations unless specifications changed.
- Once an iteration is set, we should not add epics / stories to its content. Removing content from an iteration is doable, if tasks are blocked by something not doable in the same iteration.
- At the end of an iteration, a meeting will be set to discuss the content of the next iteration and also to touch up on the different guidelines (the global and/or project specific)
- All repos will have the master branch, then a branch related to an epic, then branches related to the story of an epic.
- Pull Requests will be done from the story branch to the epic branch, once an epic is completed it will be squashed and merged to the master branch without the need for review.
- If possible, pull requests should contain medias putting the changes in display. This can be screenshots, [looms](https://www.loom.com/) or videos, whatever seems fitting as long as the changes are presented in a clear fashion.

?> CI validation could be a valid option in the future here.

- All documentation should be present and up to date on this wiki.
- Project documentation should mostly be about high level concepts, library usage and specific guidelines.
- Project should favor, if possible, libraries/packages that are from the stack ecosystem of the project.

!> This does not mean that popular and valuable libraries should be avoided at all cost. If no ecosystem dependant solution looks desirable, feel free to opt for the stack-agnostic one.

## Code Organisation

- Commit message should be descriptive and adhere to the [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0/) guidelines as mush as possible.

?> We are not currently using any semantic versioning so it is not mandatory to have strictness over the commit message content currently. Nonetheless it would help organisation to respect a certain frame in this aspect.

- Separate as mush as possible logic from display.
- Use absolute imports, unless the import is a sibling / direct child and you are sure that both the recipient and the item imported will always be linked in such a way.
- Try to follow the clean code principles as mush as possible.
- Write tests.

## Testing

- Basically, do unit tests on state logic. Do integration tests on components that have interactions.
- Test blocks should be isolated from each other. No test should depend on another running before itself.

?> End to end tests are currently not included in the scope of the project, although that might change in the future.

In term of test organisation and guidelines, you take a look at the [JavaScript Testing Best Practices](https://github.com/goldbergyoni/javascript-testing-best-practices) repository on Github.

## Clean code

Listed here are some of the most commons highlights of what defines "Clean code"

- Be clear in your variables and functions names. This means avoiding abbreviating names if said name has any sort of importance.
- Avoid [magic values](https://kyleshevlin.com/what-are-magic-values)
- If a function needs too many parameters, opt for an options object instead.
- Avoid unnecessary abstractions.
- Functions should be as pure as possible.
- Favor immutability.
- Favor declarative over imperative programming.
- Avoid comments unless they are explaining business logic or pointing to known issues

For more examples and guidelines, you can check the [Clean Code JavaScript](https://github.com/ryanmcdermott/clean-code-javascript) repository.
