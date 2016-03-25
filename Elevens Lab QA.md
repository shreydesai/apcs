# Elevens Lab Questions and Answers

## Activity 2 Questions:

1) Explain in your own words the relationship between a deck and a card.
   
```
A deck is a collection of cards.
```

2) Consider the deck initialized with the statements below. How many cards does the deck contain?

```java
String[] ranks = {"jack", "queen", "king"}; 
String[] suits = {"blue", "red"}; 
int[] pointValues = {11, 12, 13}; 
Deck d = new Deck(ranks, suits, pointValues); 
```

```
The size of the constructed deck is the product of the lengths of ranks & suits, so the answer is 6.
```

3) The game of Twenty-One is played with a deck of 52 cards. Ranks run from ace (highest) down to 2 (lowest).

```
Suits are spades, hearts, diamonds, and clubs as in many other games.
A face card has point value 10; an ace has point value 11; point values for 2, …, 10 are 2, …, 10, respectively.
```

```java
Deck d = new Deck(ranks, suits, pointValues);
 initializes a deck for a Twenty-One game. 
String [ ] ranks = {“2”, “3”, “4”, “5”, “6”, “7”, “8”, “9”, “10”, “jack”, “queen”, “king”, “ace”};
String [ ] suits = {“spades”, “hearts”, “diamonds”, “clubs”};
int [ ] pointValues = {2, 3, 4, 5, 6, 7, 8, 9, 10, 10, 10, 10, 11};
```
	
4) Does the order of elements of the ranks, suits, and pointValues arrays matter?

```
Elements of suits may appear in any order. Elements of ranks may be reordered, as ranks are not ordered in Elevens, as long as the pointValues elements are reordered in the same way. In card games where rank order is important, the sequence of elements in the ranks variable should be “in order.”
```

## Activity 3 Questions:

1) Write a static method named flip that simulates a flip of a weighted coin by returning either "heads" or "tails" each time it is called. The coin is twice as likely to turn up heads as tails. Thus, flip should return "heads" about twice as often as it returns "tails."

```java
public static String flip() {
	int r = (int) (Math.random() * 3);
	if (r < 2) {
		return “heads”; }
	else {
		return “tails”; }
}
```
	
	
2) Write a static method named arePermutations that, given two int arrays of the same length but with no duplicate elements, returns true if one array is a permutation of the other (i.e., the arrays differ only in how their contents are arranged).Otherwise, it should return false.

Two method solution 

(using a helper method):
```java
	public static boolean arePermutations (int [ ] a, int [ ] b) {
		for (int aValue : a) {
			// Make sure that every element of a is somewhere in b.
			if ( ! contains ( b, aValue) {
				return false;
			}
		}
	return true;
}

	private static boolean contains ( int [ ] b, int key ) {
		for ( int bValue : b) {
			if ( bValue == key ) {
				return true;
			}
		}
	return false;
	}
```
	
One method solution:
```
public static boolean arePermutations ( int [ ] a, int [ ] b ) {
	for ( int aValue : a) {
	// Make sure that every element of a is somewhere in b.
	boolean found = false;
	for ( int bValue : b) {
		if ( bValue == aValue ) {
			found = true;
		}
	}
	if ( ! found ) {
		return false;
	}
	}
	return true;
}
```


3) Suppose that the initial contents of the values array in Shuffler.java are {1, 2, 3, 4}. For what sequence of random integers would the efficient selection shuffle change values to contain {4, 3, 2, 1}? 

```
The sequence 0, 1, 1. The first 0 switches 4 and 1, producing 4, 2, 3, 1; the first 1 switches 2 and 3, producing 4, 3, 2, 1; and the second 1 switches the 3 with itself.
```

## Activity 6 Questions:

1) List all possible plays for the board 5♠ 4♥ 2♦ 6♣ A♠ J♥ K♦ 5♣ 2♠

```
The 5♠ with the 6♣ make 11. The 5♣ with the 6♣ also make 11.
```

2) If the deck is empty and the board has three cards left, must they be J, Q, and K? Why or why not?

```
The deck and the board satisfy three invariant relations before and after each play.
- The number of face cards in the deck plus the number of face cards in the board is divisble by 3.
- The number of jacks, the number of queens, and the number of kings are all equal to each other.
- The number of nonface cards in the deck plus the number of nonface cards in the board is even.
Thus, if the deck is empty and the board contains three cards, they must all be face cards. Because there have to be equal numbers of each face card, the three must be the remaining JQK.
- If there are three face cards left, there must have been three previous plays of face cards. If the remaining cards are not JQK, then each face card rank wasn’t played the same number of times. This can’t happen.
- If there are two or one face cards left, we get a contradiction using the same reasoning as in the first case.
- If none of the three cards is a face card, there must have been a play of an odd number of nonface cards earlier in the game, as there are 40 nonface cards in all. This play would have been illegal.
```


3) Does the game involve any strategy? That is, when more than one play is possible, does it matter which one is chosen? Briefly explain your answer.

```
The game doesn’t involve any strategy. When there is a choice between two or more different plays, it doesn’t matter in which order they are played.
```


## Activity 7 Questions:

1) What items would be necessary if you were playing a game of Elevens at your desk (not on the computer)? List the private instance variables needed for the ElevensBoard class.

```
Deck of cards and a list of cards on the board. The ElevensBoard class would need Deck and Card [] instance variables.
```

2) Write an algorithm that describes the actions necessary to play the Elevens game.
Answers may vary. One possible answer is:
```
Shuffle the deck;
Deal nine cards;
While there is a possible move, 
	If a pair exists that sums to 11,
		Remove the pair;
		Replace the two removed cards if possible;
	Else if a triplet that contains J, Q, K exists,
		Remove the triplet;
		Replace the three removed cards if possible;
If there are no cards left on the board, you win, or else you lose.
```

3) Now examine the partially implemented ElevensBoard.java file found in the Activity7 Starter Code directory.
Does the ElevensBoard class contain all the state and behavior necessary to play the game?

```
In the ElevensBoard class, as written, there are no methods that actually select the cards to be removed, only ones to check 
already selected cards.
```

4) ElevensBoard.java contains three helper methods. These helper methods are private because they are only called from the ElevensBoard class.
a) Where is the dealMyCards method called in ElevensBoard?

```
The method, dealMyCards, is called in the ElevensBoard constructor and the newGame method.
```

b) Which public methods should call the containsPairSum11 and containsJQK methods?

```
The methods isLegal and anotherPlayIsPossible should call the containsPairSum11 and containsJQK methods.
```

c) It’s important to understand how the cardIndexes method works, and how the list that it returns is used. Suppose that cards contains the elements shown below. Trace the execution of the cardIndexes method to determine what list will be returned. Complete the diagram below by filling in the elements of the returned list, and by showing how those values index cards. Note that the returned list may have less than 9 elements.

d) Complete the following printCards method to print all of the elements of cards that are indexed by cIndexes.

```java
public static printCards(ElevensBoard board) {
      List cIndexes = board.cardIndexes(); 
      /* Your code goes here. */

       } 
public static printCards ( ElevensBoard board ) {
	List < Integer > cIndexes = board.cardIndexes ( );

	for ( Integer kObj : cIndexes ) {
		int k = kObj.intValue ( );
		System.out.println ( board.cardAt ( k ) ) ;
	}
}
```

e) Which one of the methods that you identified in question 4b above needs to call the cardIndexes method before calling the containsPairSum11 and containsJQK methods? Why?

```
The method anotherPlayIsPossible needs to call the cardIndexes method before calling the containsPairSum11 and containsJQK methods. It needs to do this in order to get the indexes of all the cards on the board ( non-null cards) so that it can check to see if the board contains another pair of cards that sum to 11 or a JQK-triplet.
```

## Activity 8 Questions:

1) Discuss the similarities and differences between Elevens, Thirteens, and Tens.

Similarities:

```
They are all single player games.
They are all played on a board with cards.
The cards are selected for removal based on one of two rules: the cards’ point values add up to a specific sum, or there is a specific group of face cards.
```

Differences:

```
The number of cards on the board is different.
The sums differ.
The specific groups of face cards differ.
```

2) As discussed previously, all of the instance variables are declared in the Board class. But it is the ElevensBoard class that “knows” the board size, and the ranks, suits, and point values of the cards in the deck. How do the Board instance variables get initialized with the ElevensBoard values? What is the exact mechanism?
The ElevensBoard constructor passes to the Board constructor the information needed to initialize the instance variables declared in the abstract Board class. This is accomplished through the following use of super:

```java
super ( BOARD_SIZE, RANKS, SUITS, POINT_VALUES );
```
	
3) Now examine the files Board.java, and ElevensBoard.java, found in the Activity8 Starter Code directory. Identify the abstract methods in Board.java. See how these methods are implemented in ElevensBoard. Do they cover all the differences between Elevens, Thirteens, and Tens as discussed in question 1? Why or why not?

```
No. The abstract methods will have to be implemented differently in the Tens and Thirteens games and will need different private helper methods to accomplish their tasks.
```
