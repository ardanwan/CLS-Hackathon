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

| Pay-off Matrix | Necrosis (q), m: ITMs neutralized by granules pernecrotic neutrophil | Apoptosis (1 − q), n: ITMs neutralized by granules per apoptotic neutrophil |
|:-----------------:|:----:|:-----:|
| Necrosis (p)      | A, A | B, C |
| Apoptosis (1 − p) | C, B | D, D |

We specify the payoffs of the neutrophil game asfollows:
- A = −c<sub>Necrosis</sub>
- B = −c<sub>Necrosis</sub> + b<sub>Apoptosis</sub>
- C = b<sub>Apoptosis</sub>
- D = 2b<sub>Apoptosis</sub>

First, we create an empty lattice of size 50 × 50. In our
model, the entire lattice space is interpreted to correspond to a small portion of tissue. In order to model a
bigger tissue that represents the entire body, we use
periodic boundary conditions in our simulations. Additionally, since we assume a systemic inflammation,
where ITMs are simultaneously originating from various
sources in the body, we assume that the concentration
of ITMs are equally distributed all over the simulated
lattice. This follows that the distribution of the neutrophils
in the tissue should also be homogenous. Hence, a single
lattice site is occupied by a neutrophil entity, which, in the
context of our model, refers to the neutrophil cell and the
tissue the neutrophil occupies. The 50 × 50 lattice site,
therefore, contains a total of 2500 neutrophils.

ITMs are introduced homogenously by distributing
the total ITM concentration equally in the lattice. In the
simulation, this is simply calculated by assigning the
concentration of ITMs to a global value that is neutralized at every time step.

The algorithm commences by choosing an activated
neutrophil randomly inside the 50 × 50 lattice that is initially filled with 2500 activated neutrophils. The chosen
activated neutrophil plays the game based on the payoffs
summarized in the above table with all of its immediate neighbors in a Moore neighborhood of range equal to 1.
The choice of strategy of an activated neutrophil is
decided based on a fitness comparison made by choosing
either strategy. The payoff the activated neutrophil gets
from playing with all its immediate neighbors is reduced
by the cost of the remaining ITMs in the system. The final pay-off that decides the startegy to adopt is thus
- (Payoff from Neurophil game with all necrotic/apoptotic neighbours) - e<sup>αITMS<sub>remaining</sub></sup>
When the payoff for going into apoptosis is exactly the
same as deciding on necrosis, the activated neutrophil
takes the apoptotic pathway. We model it this way
because we assume that apoptosis is the default pathway
that neutrophils take with or without inflammation. It is
after all a type of programmed death that take place
regardless of the intensity of inflammation


