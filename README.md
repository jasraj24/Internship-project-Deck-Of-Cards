# Internship Project Deck of Cards

# Java Code

import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
import java.util.Random;

// Enum for card suits
enum Suit {
    SPADE,
    CLUB,
    HEART,
    DIAMOND
}

// Enum for card ranks
enum Rank {
    ACE, TWO, THREE, FOUR, FIVE, SIX, SEVEN, EIGHT, NINE, TEN, JACK, QUEEN, KING
}

// Card class representing a single card
class Card {
    private Suit suit;
    private Rank rank;

    public Card(Suit suit, Rank rank) {
        this.suit = suit;
        this.rank = rank;
    }

    public Suit getSuit() {
        return suit;
    }

    public Rank getRank() {
        return rank;
    }

    @Override
    public String toString() {
        return rank + " of " + suit;
    }
}

// Custom comparator to sort cards based on color, suit, and rank
class CardComparator implements Comparator<Card> {
    @Override
    public int compare(Card card1, Card card2) {
        // Compare based on color
        int colorComparison = getColorValue(card1.getSuit()) - getColorValue(card2.getSuit());
        if (colorComparison != 0) {
            return colorComparison;
        }

        // Compare based on suit within each color
        int suitComparison = card1.getSuit().compareTo(card2.getSuit());
        if (suitComparison != 0) {
            return suitComparison;
        }

        // Compare based on rank
        return card1.getRank().compareTo(card2.getRank());
    }

    // Helper method to determine color value
    private int getColorValue(Suit suit) {
        return (suit == Suit.HEART || suit == Suit.DIAMOND) ? 0 : 1;
    }
}

// Deck class to manage the deck of cards
class Deck {
    private List<Card> cards;

    public Deck() {
        cards = new ArrayList<>();
        // Initialize the deck with 52 cards
        for (Suit suit : Suit.values()) {
            for (Rank rank : Rank.values()) {
                cards.add(new Card(suit, rank));
            }
        }
    }

    // Shuffle the deck
    public void shuffle() {
        Collections.shuffle(cards);
    }

    // Draw a specified number of cards from the deck
    public List<Card> draw(int numCards) {
        if (numCards > cards.size()) {
            throw new IllegalArgumentException("Not enough cards in the deck");
        }
        List<Card> drawnCards = new ArrayList<>();
        for (int i = 0; i < numCards; i++) {
            drawnCards.add(cards.remove(0));
        }
        return drawnCards;
    }

    // Get the size of the deck
    public int size() {
        return cards.size();
    }
}

public class Main {
    public static void main(String[] args) {
        Deck deck = new Deck();
        deck.shuffle(); // Shuffle the deck

        // Draw 20 cards from the deck
        List<Card> drawnCards = deck.draw(20);

        // Sort the drawn cards using custom comparator
        Collections.sort(drawnCards, new CardComparator());

        // Print the sorted drawn cards
        for (Card card : drawnCards) {
            System.out.println(card);
        }
    }
}


# By Jasraj Singh
