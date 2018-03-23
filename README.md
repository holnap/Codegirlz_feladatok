# Codegirlz_feladatok

Hello,

This is what I made, I couldn't finish all the exercises. I worked in Phyton.

Best wishes,

Zsuzsi

1.Create a function that takes a list of numbers as parameter and returns the average value of the odd
numbers in the list.

	def remove_even(numbers) :

    	new_list = []
		
	for i in range(0,len(numbers)) :

  	if i % 2 != 0 :
	
    	new_list.append(i)
		
	return new_list
		
	l = [1,2,3,4,5,6,7,8,9,10]

	paratlanok = list(remove_even(l))

	osszpar = sum(paratlanok)

	hossz = len(paratlanok)

	atlag = osszpar/hossz

	print (atlag)


2. Create a function that takes a text as a parameter and returns an encoded version of the text according
to the following algorithm:

● each letter in the text is replaced by a letter some fixed number of positions up in the alphabet

● the number of this shifting positions equals to the number of occurrences of the first letter in
the whole text

● the algorithm works with lower case letters, it modifies upper case letters to lower case ones as
well

● the special characters (e.g. spaces, exclamation mark, ...) remain the same

● shifting a letter towards the end of the alphabet continues from the beginning of the alphabet (
z → a)

		myword = ('hellohaho')

		p = myword.count(myword[0])

		myword = myword.lower().replace(" ", "")

		for i in myword:

    		print(chr(ord(i) + p))
		
    
3. Card class
Create a Card class, that has a color and a value.
Create a constructor for setting those values
Card should be represented as string in this format:

● 9 Hearts

● Jack Diamonds

Deck class
Create a Deck class, that has a list of cards in it.

Create a constructor that takes a whole number as parameter.

The constructor should fill the list with the number of different cards using at least 4 different colors
(except if the number given is smaller than four, than all cards should have different colors).

We should be able to shuffle the deck, which randomly orders the cards.

We should be able to draw the top card which returns the drawn card and also removes it from the
deck.

Each card only occurs once in the deck.

Deck should be represented as string in this format:

● 12 cards - 3 Clubs, 3 Diamonds, 3 Hearts, 3 Spades

I didn't have time to do this task, so I looked for a solution on Stockoverflow and studied it.

	def __init__(self, rank, suit):

        self.ranks = [None, "Ace", 2, 3, 4, 5, 6, 7, 8, 9, 10, "Jack", "Queen", "King"]
				
        self.rank = self.ranks[rank]
				
        self.suits = {"d": "Diamonds", "c": "Clubs", "h": "Hearts", "s": "Spades"}
				
        self.suit = self.suits[suit]
				
        self.value = -1

    def getRank(self):
        return self.rank

    def getSuit(self):
        return self.suit

    def bjValue(self):
        if self.rank == "Ace":
            self.value = 1
        elif self.rank == "Jack" or self.rank == "Queen" or self.rank == "King":
            self.value = 10
        elif type(self.rank) is int:
            if self.rank > 1 and self.rank < 11:
                self.value = self.ranks[self.rank]
        return self.value
