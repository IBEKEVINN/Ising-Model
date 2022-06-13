# Ising-Model

The Ising model is an idealized study of magnetic behaviour in a solid. In the model, there is a regular
n-dimensional grid of electrons with spin 𝑆 that can have a value of +1 or -1, which can only interact
with their nearest neighbours.

The python file in this repo contains a class that represents the lattice of the solid. After it has been called 
with initial starting variables, the inbuilt functions can be used to calculate and plot the total energy, magnetic 
susceptibility and spin direction.

## The model's approach

The Ising model code uses a probabilistic approach and a series of steps to find the lowest energy
state of the lattice, across a range of temperatures. For each temperature step, it begins with either a 'cold' start, 
in which all the spins are aligned, or a 'hot' start, in which the spins are randomly set. It then randomly chooses one of the 
electrons and uses a Metropolis algorithm to decide whether to flip it.

The algorithm works like this:

1. If flipping the spin would reduce the total energy, flip it
2. If flipping the spin would increase the total energy by an amount dE, draw a random number between 0 and 1 and flip it if the number is smaller then exp(-dE/kT).

This process is repeated until the system reaches equilibrium; that is, until the energy stops
decreasing at each step (a cap can be set). Then the code increases the temperature, resets the
lattice to initial conditions, and runs the steps again.



