# Introduction

Neutrophils play a crucial role in the human innate
immune response. These human immune cells are not
only the most abundant among immune cells, but also
are the first to arrive at the sites of insult, where they
execute their anti-inflammatory functions. Approximately 1011 neutrophils circulating in the bloodstream undergo programmed cell death, also known
as apoptosis, per day. Neutrophils still undergo this
natural death process even under healthy conditions in
order to maintain homeostasis. In case of an insult,
inflammation triggering moieties (ITMs) like bacterial
lipopolysaccharides (LPS) and extracellular nucleotides
induce inflammation, an essential mechanism of the
innate immune response. These ITMs are phagocytosed by active neutrophils or neutralized through the
release of granules, depending on the nature of the
ITMs. When inflammation is easily resolvable by the
available population of immune cells at the site of inflammation, previously active neutrophils proceed to apoptosis.

However, if the inflammation is too intense or persistent, such as in systemic inflammation where ITMs are
simultaneously originating from various sources in the
body, neutrophils take on a dangerous death pathway
called necrosis. Necrosis is a violent cell death that involves the rupture of the cell membrane, spilling out its
cytoplasmic contents into the site of inflammation, thus
further aggravating the inflammation. Necrosis is one of
the major causes of tissue damage during inflammation,
contributing to sepsis and potentially leading to lethal
complications during the inflammation. It has been observed that the proportion of neutrophils going into either
death pathway depends on the scale of the insult.
The intricate details and the underlying mechanisms
regarding the resolution of inflammation by neutrophils is
still an active evolving field.

# Assignment
We're going to build the game of Neurophils using cellular automata and evolutionary game theory. The neutrophil game is a two-player game that utilizes one of the two strategies namely: necrosis or apoptosis.
The payoffs for each pair of strategies are summarized in
the table below. A row corresponds to the strategy played by
player 1 and a column corresponds to the strategy played
by player 2. The neutrophil game follows a mixed strategy
game, meaning that we assign a probability for each strategy. This allows a player to probabilistically choose between apoptosis and necrosis. The rationale behind this
choice is that the pathways leading to apoptosis or necrosis depend on a series of biochemical reactions in response
to external stimuli and internal processes of the cell. All
these processes are stochastic, so that a cell exposed to a
given environment might take one pathway or the other
with a certain probability. In our model, player 1 chooses
to go into necrosis with a probability q and apoptosis with
a probability (1 − q). Player 2, on the other hand, chooses
to go into necrosis with a probability p and apoptosis with
a probability 1 − p.

| Payoff Matrix |f the Neutrophi| Game  |
| ------------- |:-------------:| -----:|
| col 3 is      | right-aligned | $1600 |
| col 2 is      | centered      |   $12 |
| zebra stripes | are neat      |    $1 |
