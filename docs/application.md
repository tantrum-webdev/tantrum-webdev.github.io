# Application Features

Basically, this application allows its users to add deck lists, either imported or created from scratch via the app. Lists can also be exported to use in other applications, eg. Magic Arena.

On its initial planning, there would be three different pages :

- Home: Where the user can consult his deck lists, export them, import or create a new one.
- Deck: Where the user can consult an existing deck, edit it or create a new one altogether.
- Error: Typically a 404/500 page.

## What is a deck

A deck represent a set list of cards in 'Magic: The gathering'. Given a set of restrictions, a set must contain at least a specified number of cards (usually 40, 60 or 100).

Aside from those cards, a deck can also contain what is called a sideboard: cards that are a reserve, allowing the player to switch them from others currently in his deck between two games in a bo-x series in order to modify his strategy.

Cards are listed in differents sets, a definite collection of cards that are released in a span of several months between each other. In a set, a card can be newly printed (never seen before) or be a reprint (existed in a previous set, either in the same type or not). A reprint usually offers new artwork, and sometimes, revised rarity.

## Home page

Specific to this page, the main element would be a container displaying the list of decks already existing for a specific user and options to customize the display and content of said list.

!> If a user has no existing deck to display, a replacement component should be displayed, offering the user call to actions buttons to either import or create a new deck.

### Types of display

The base layout would be a table display, showing deck informations like name, type(eg: standard, commander, limited), colors.

?> WIP Mockup of the table display

Another could be a card display, having small deck cards layered in a grid, including a thumbnail of choise for each deck with most of the previous information.

?> WIP Mockup of the card display

Other layout options are open to suggestions.

### List manipulation

To allow the user to render the list according to his preferences or needs, a container would be displayed, within it different buttons or fields.

- A user should be able to easily switch between displays.
- A user should be able to start a text search over his decks. This option would search against eg: deck names, types, colors.
- A user should be able to filter his deck lists, options could be by type (only standard decks), by color(eg: should contain green), by deck completion (eg: only complete and valid decks).
- In this bar there should also be a button allowing the user to export his deck.

?> Import/export features need to be defined and will be explored later on.

## Deck page

This page would contain two different and related modes : `view` and `edit`.

### View mode

In viewing mode, the user would be able to check the meta informations of his deck (eg: name, type, color, thumbnail), its cards and statistics (eg: mana distribution, color distribution)

### Edit mode

In edit mode, the user would be able to update the meta informations of his deck and update the card list by searching for new cards to add to his deck or others to remove.

Deck edition would need to take into account the restrictions of its type. For example, a Standard deck would need to respect these restrictions :

1. At least 60 cards
2. Can contain only cards from the X most recent sets except for reprints
3. Only 4 copies of the same card name, regardless of reprints
4. Have up to 15 cards in the sideboard. Previous rules also apply to the sideboard. Number of copies count both the main decklist and the sideboard.

Adding to these restriction, a type can contain what is called a ban list, cards that are not legal in competitive games of said types.

Not respecting any of the aforementioned rules and/or having cards that are not type legal would set the current deck with a flag, specifying that it can't be used in competitive play.

If a deck is flagged this way, the user needs to find an easy way to figure out the changes required to have his deck legal, either by changing the type or updating the card list.

### Card searching

The topic of card search can be tricky, given that MTG spans 30 years and thousands of cards exist and are addable to decklists. The most logical way to implement this feature would be to have a search field, allowing the user to search a specific card. The results should provide, if possible, some filtering based on deck options (eg: do not show card results that are not available in said type). Those results could be displayed in a tooltip near the search field.

## Error page

This page would be displayed if the user tries to access a url that is not handled by the router.

It would contain a way to go back to the home page and a simple message explaining how or why the user sees this content.
