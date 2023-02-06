# E-Card
#### Video Demo:  https://youtu.be/_jL6glALfUo
#### Description:

## About this project

I made a game called "E-Card" with Python.
The game is based on a Japanese comic, ["Gambling Apocalypse: Kaiji(Tobaku Mokushiroku Kaiji)"](https://en.wikipedia.org/wiki/Kaiji_(manga)).

## What is the "E-Card"?


E-Card is a type of card game played by two players with a set of five cards.
Each player begins with five cards: either one Emperor and 4 Citizen cards or one Slave card and four Citizen cards. Let's refer to the player with the Emperor card as the "Emperor side", and the player with the Slave card as the "Slave side".

You can choose which side to play soon after starting the program, but you must change sides every three games. Over the course of 12 total games, you will play the side you initially selected for the first three games, then switch to the opposite side for games four to six. After that, you will play the same side as the first three games before switching sides for the last three games again.

For example, if you chose Emperor side firstly, you play that side at 1st 3 games and from 7th to 9th games, and play Slave side from 4th to 6th games and from 10th to 12th games and vice versa.

To play the game is so simple. 1 game has 5 turns, and you choose 1 card and submit it in each turn.
The opponent(computer) also submit a card at the same time.

If both players choose Citizen cards, the turn results in a draw and play continues to the next turn.
If the cards chosen by both players are different, the game ends and the player is either awarded a prize or loses length (mm) before proceeding to the next game.

Concretely to say:

**if the Emperor card is submitted against the Citizen, the Emperor wins.**

**if the Citizen card is submitted against the Slave, the Citizen wins.**

**if the Slave card is submitted against the Emperor, the Slave wins.**

So the game can end in the 1st turn or go through to 5th turn.
If you submitted all 4 Citizens and the opponent did the same, you don't need to choose the card in 5th turn.
In case the game comes to 5th turn, Slave side certainly wins as the rest of cards are only Emperor and Slave.

You repeat that cycle for 12 games.

It is simple, isn't it?

## What do you bet in the game and what is the reward?

As this game derives from a story about gambling, the player have to bet something.
In the original story, the hero named Kaiji bet the length of the depth of his ear canal, which was 30 mm from the entrance to his eardrum.
A machine with a needle was attached to one of his ear.
He could bet each length in unit of mm and if he lose all of those 30 mm, his eardrum will be pierced by the needle.

You can find the detail here: [Ear and Eye Drills](https://kaiji.fandom.com/wiki/Ear_and_Eye_Drills)

The page is not graphic, so you don't have to worry.

In this game, you can also bet the "30 mm" length of the ear canal, just like in the original story. You can bet by entering an integer at the beginning of each game (you have 12 chances to bet). When you lose, the length decreases, and if you run out of those 30 mm, you can no longer play even if you haven't completed all 12 games.

Winning the game means earning money. When playing the Emperor side, you receive 1,000 USD per mm, while playing the Slave side earns you 5,000 USD per mm. The prize for playing the Slave side is higher because it's more difficult to win.

For example, if you have 30 mm and bet 1 mm as the Emperor side and win, you receive 1 * 1,000 = 1,000$.
If you lose, you lose 1 mm and in the next game, you can bet 1 mm to 29 mm.

If you have 15 mm and bet 10 mm as Slave side and win, you receive 10 * 5,000 = 50,000$!
If you lose, you lose 10 mm, and in next game, you can bet only 5 mm.

I suggest that you first decide how much money you want to earn so that you can enjoy the game in a more strategic way!

Lastly, I have one unpleasant and one pleasant news to share with you.
The bad one is that you won't be able to transfer your earnings from the game to your bank account unfortunately.
The good one is that your eardrum will be completely safe even if you lose the game!


## How to play the game

The instructions for playing the game are as follows:

1. Choose which side to play first by entering "E" or "e" for Emperor side, "S" or "s" for Slave side.
2. Decide how much length to bet in the first game by entering integer from 1 to 30.
3. Choose which card to submit by entering "E" or "e" for Emperor, "C" or "c" for Citizen, "S" or "s" for Slave.
4. Repeat step 3 until the game is decided.
5. After the game is over, proceed to the next game if you have length remaining.
6. Choose how much length to bet in the next game by entering an integer from 1 to the remaining length.
7. Repeat steps 3 to 6 until all 12 games are over.

In each turn, the information on the number of games and turns, as well as the cards you have, will be displayed so you can easily keep track of the situation.

Good luck!

## Reference for E-Card
You can find the game's details in the website below if you are more interested:
[E-Card](https://kaiji.fandom.com/wiki/E-Card)

## Structure of this program

This program contains only 1 file, "project.py".
Only 1 library "Random" is used in it.

The file "project.py" works for the all parts of the game described above.
The game's conditions are saved in the dictionary called "status" and it's passed around through several important functions like "setup_card", "submission", and "decision". Those functions works to recognize the situation and control the flow of the game correctly.
