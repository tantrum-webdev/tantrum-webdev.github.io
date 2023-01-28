# Application Features

As a reminded, here are the base stories a user should be able to :

- See the list of decks.
- Create a new deck from scratch.
- Import a deck from another source.
- Look at the content of an existing deck.
- Edit the content of an existing deck.
- Export a deck as a text file.

On its initial planning, there would be three different pages :

- Home: Where the user can consult his deck lists, export them, import or create a new one.
- Deck: Where the user can consult an existing deck, edit it or create a new one altogether.
- Error: A 404/500 page.

## What is a deck

A deck represent a set list of cards in 'Magic: The gathering'. Given a set of restrictions, a set must contain at least a specified number of cards (usually 40, 60 or 100). Some decks can include a sideboard: cards available to switch from a deck between games of a match.

Cards come from a set: a finite collection of cards released in a span of several months between each other. In a set, a card can be original (never printed before), or can be a reprint (existed in a previous set). A reprinted card is the same as the original except its artwork, and in some cases, its rarity.

## Home page

This page should have a container to display existing decks. If no deck exists, a section to suggest creating a new deck replaces the previous container.

### Types of display

Initial layout is a responsive table showing deck information (name, format, colors used, …).

?> WIP Mockup of the table display

One other available layout is a card display. Inside a grid, show each deck with a thumbnail image and the same information as the table display.

?> WIP Mockup of the card display

Other layout options are open to suggestions.

### List manipulation

The user needs to be able to alter the content of the deck list, display or content wise:

- A user should be able to switch between displays.
- A user should be able to start a text search over his decks. This option would search against eg: deck names, types, colors.
- A user should be able to filter his list based on different criteria.

## Deck page

This page would contain two different and related modes : `view` and `edit`.

### View mode

The user can see:

- the cards contained in the deck.
- the deck information
- statistics of the deck (mana, color, type distributions)

### Edit mode

The user can change the deck information or cards.

Deck edition would need to take into account the restrictions of its type.

> For example, a Standard deck would need to respect these restrictions :
>
> 1. At least 60 cards
> 2. Can contain only cards from the X most recent sets except for reprints
> 3. Only 4 copies of the same card name, regardless of reprints
> 4. Have up to 15 cards in the sideboard. Previous rules also apply to the sideboard. Number of copies count both the main decklist and the sideboard.

Some cards are also banned from specific formats.

A deck becomes illegal to play in a format if it contains a banned card or doesn't apply all the specifications. In such a case, we need to inform the user via the UI.

### Card searching

To create or update a deck, the user needs to be able to search cards.
This topic can be complex and will need discussions to establish the specifics.

## Error page

This page appears if the user tries to access a page that doesn't exist or if the request encounters an error.

It would contain a way to go back to the home page and a simple message explaining how or why the user sees this content.
