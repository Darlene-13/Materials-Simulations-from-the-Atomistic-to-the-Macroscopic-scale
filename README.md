# Materials-Simulations-from-the-Atomistic-to-the-Macroscopic-scale
Materials Simulations from the Atomistic to the Macroscopic scale



Schronider equation enables one to compute the possible energy states of a quantum mechanical system. 
It is a fundamental equation in quantum mechanics that describes how the quantum state of a physical system changes over time.



Schronider equation is given by:
iħ ∂ψ/∂t = Hψ 

Where:
- i is the imaginary unit
- ħ is the reduced Planck's constant
- ψ (psi) is the wave function of the quantum system
- H is the Hamiltonian operator, which represents the total energy of the system

The Schronider equation can be solved to find the wave function ψ, which contains information about the probability distribution of a particle's position and momentum.




## GROUND STATE ENERGY CALCULATION
Definition:
Ground state energy refers to the lowest possible energy  that a quantum mechanical system can have.
It is the energy of the system when it is in its most stable configuration, with all particles occupying the lowest available energy levels. a simple quantum harmonic oscillator:
```python
import numpy as np
from scipy.linalg import eigh
# Define constants
hbar = 1.0545718e-34  # Reduced Planck's constant
m = 9.10938356e-31    # Mass of electron
omega = 1.0e15        # Angular frequency
# Define Hamiltonian matrix for a quantum harmonic oscillator
def hamiltonian_matrix(n):
    H = np.zeros((n, n))
    for i in range(n):
        H[i, i] = hbar * omega * (i + 0.5)
        if i < n - 1:
            H[i, i + 1] = H[i + 1, i] = -hbar * omega / 2
    return H
# Number of energy levels
n_levels = 10
H = hamiltonian_matrix(n_levels)
# Solve the Schronider equation (eigenvalue problem)
eigenvalues, eigenvectors = eigh(H)
# Ground state energy
ground_state_energy = eigenvalues[0]
print(f"Ground State Energy: {ground_state_energy} J").

```



Ground State Energy Calculation
To calculate the ground state energy of a quantum system using the Schronider equation, one typically follows these steps:
1. Define the Hamiltonian (H) of the system, which includes kinetic and potential energy terms.
2. Set up the Schronider equation with the defined Hamiltonian.
3. Solve the Schronider equation for the wave function ψ.
4. Calculate the expectation value of the Hamiltonian using the wave function to find the ground state energy.
Here is a simple example using Python and the NumPy library to calculate the ground state energy of