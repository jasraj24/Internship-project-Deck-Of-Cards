# Internship Project Deck of Cards

This Java project simulates a standard deck of playing cards and provides functionality to shuffle the deck, draw a specified number of cards, and sort them based on a custom sorting criterion.

**Brief Overview:**

- **Deck Management:** The `Deck` class manages a deck of cards, allowing initialization with 52 cards, shuffling, drawing a specified number of cards, and querying the size of the deck.

- **Card Representation:** The `Card` class represents a single card with attributes for suit and rank. It provides a readable string representation of each card.

- **Custom Sorting:** The `CardComparator` class implements a custom comparator to sort cards based on color, suit, and rank. Cards are first sorted by color (red or black), then by suit, and finally by rank.

**Functionality:**

1. **Deck Initialization:** Upon creation, the `Deck` class initializes with 52 cards representing each combination of suit and rank.

2. **Shuffling:** The `shuffle` method shuffles the deck randomly, ensuring that cards are in a random order.

3. **Drawing Cards:** The `draw` method allows drawing a specified number of cards from the deck. If there are not enough cards in the deck, it throws an exception.

4. **Sorting:** After drawing cards, the `Main` class sorts them using the custom comparator, ensuring they are ordered by color, suit, and rank.

5. **Output:** The sorted cards are then printed to the console, showing the order in which they were drawn but sorted based on the custom sorting criterion.

Overall, this project serves as a foundational framework for implementing card games or any application requiring deck management and card sorting functionality.

# By Jasraj Singh
