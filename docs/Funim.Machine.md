# Funim.Machine

Defined in funim@0.5.5

State machine library

## Values

### namespace Funim.Machine::Machine

#### compose

Type: `Funim.Machine::Machine o1 o2 -> Funim.Machine::Machine i o1 -> Funim.Machine::Machine i o2`

Compose two machines.

#### from_transition

Type: `s -> (i -> s -> (s, o)) -> Funim.Machine::Machine i o`

Create an object from the initial state and state transition function

#### from_transition_io

Type: `s -> (i -> s -> Std::IO (s, o)) -> Funim.Machine::Machine i o`

Create an object from the initial state and state transition function with IO

#### identity

Type: `Funim.Machine::Machine i i`

Create a machine that outputs the input as is.

#### integrate

Type: `[o : Std::Additive] Funim.Machine::Machine o o`

Create a machine that calculates the cumulative sum of inputs.

The first output is 0, and subsequent outputs are the cumulative sum of inputs up to that point.

#### parallel

Type: `Std::Array (Funim.Machine::Machine i o) -> Funim.Machine::Machine i (Std::Array o)`

#### run

Type: `i -> Funim.Machine::Machine i o -> Std::IO (Funim.Machine::Machine i o, o)`

Advance the machine by one step

#### zip

Type: `Funim.Machine::Machine i o2 -> Funim.Machine::Machine i o1 -> Funim.Machine::Machine i (o1, o2)`

Zip two machines.

## Types and aliases

### namespace Funim.Machine

#### Machine

Defined as: `type Machine i o = unbox struct { ...fields... }`

A state machine that takes input of type i, changes its internal state, and outputs a value of type o

##### field `_run`

Type: `i -> Std::IO (Funim.Machine::Machine i o, o)`

## Traits and aliases

## Trait implementations

### impl `Funim.Machine::Machine i : Std::Functor`