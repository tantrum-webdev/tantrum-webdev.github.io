# Set of Guidelines

## Work Organisation

To organize development, milestones will be set. A milestone is a collection of epics and stories, grouped to complete together. Once done, we define a new milestone. This is like the usual sprint philosophy, except that we don't have time constraints.

For the specifics :

- Make sure that issues contain enough information and what are the validation criteria
- A story is an issue assigned to an epic. This doesn't mean that all issues are stories though.
- An epic is a set of stories grouped by context. For example, all stories related to the card search feature(s) are in the same `Search` epic.
- A milestone contains one or several epics. Avoid setting up epics that aren't closable in one milestone if possible.
- Do not add epics / stories to a set milestone. You can remove from it if it contains blocked content though.
- At the end of each milestone, a meeting is set up. During the meeting, three things are in order. Define the next milestone. Discuss changes to guidelines. Make sure documentation is up to date.
- All repos will have the master branch, a branch related to a milestone, then branches related to a story.
- Pull Requests go from a story branch to a milestone branch. Once we complete a milestone, squash and merge its branch to the master.
- Pull Requests descriptions need to contain informations about the changes. List of modifications, screenshots, [looms](https://www.loom.com), videos, etc.
- Opt for ecosystem specific packages if other stack agnostic proposals are similar.

## Code Organisation

- Commit message should be in the form of `M<milestone number>-#<issue number>-<message>`. Example : `M1-#1-Install msw package`

?> We are not currently using any semantic versioning so it is not mandatory to have strictness over the commit message content currently. Nonetheless it would help organisation to respect a certain frame in this aspect.

- Separate as mush as possible logic from display.
- Use absolute imports unless importing a sibling or child if its path will stay the same.
- Try to follow the clean code principles as mush as possible.
- Write tests.

## Testing

- Do unit test on logic. Do integration tests on components that have interactions.
- Coverage % is not the be all end all but still provides good information about what is not covered.
- Do tests in isolation from each other. No test should depend on another running before itself.

?> You can check the [JavaScript Testing Best Practices](https://github.com/goldbergyoni/javascript-testing-best-practices) repository on Github to check best practices and guidelines on testing.

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
