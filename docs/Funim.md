# Funim

Defined in funim@0.5.5

## Values

### namespace Funim

#### clock

Type: `Funim.Machine::Machine Funim::TimeDelta Funim::Time`

The machine that outputs the current time.

#### run_animation

Type: `Funim::Animation -> Funim::Config -> Std::IO ()`

Create a window and run the animation

##### Parameters

* `animation`
* `config`

### namespace Funim::Animation

#### buffered

Type: `MiscAlgos.Geometry::Rectangle -> Funim::Animation -> Funim::Animation`

Draw the animation through a dedicated buffer.

The first argument is a rectangle that specifies the range to buffer.

The buffer is not cleared automatically.

#### stack

Type: `Std::Array Funim::Animation -> Funim::Animation`

Stack multiple animations.

#### translate

Type: `MiscAlgos.Geometry::Vec2 -> Funim::Animation -> Funim::Animation`

Translate the position of the animation

### namespace Funim::Config

#### default

Type: `(Std::I64, Std::I64) -> Funim::Config`

Create a default configuration.

- The desired fps is set to 30.0.

##### Parameters

* `size`

#### encode

Type: `(Std::I64, Std::I64) -> Funim::Time -> Std::Path -> Funim::Config`

Create a configuration for encoding.

- The desired fps is set to 30.0.
- The fixed_fps is set to true.

##### Parameters

* `size`
* `time`
* `out_path`

### namespace Funim::Draw

#### stack

Type: `Std::Array Funim::Draw -> Funim::Draw`

Stack multiple drawing operations.

#### translate

Type: `MiscAlgos.Geometry::Vec2 -> Funim::Draw -> Funim::Draw`

Translate the drawing position.

## Types and aliases

### namespace Funim

#### Animation

Defined as: `type Animation = Funim.Machine::Machine Funim::TimeDelta Funim::Draw`

Type representing an animation.

An animation is a machine that takes the elapsed time since the last frame as input and outputs the drawing process at the current time.

Note: The origin of the coordinate system for the drawing is the center of the screen (not the top left).

#### Config

Defined as: `type Config = box struct { ...fields... }`

Animation configuration

##### field `size`

Type: `(Std::I64, Std::I64)`

Screen size

##### field `fps`

Type: `Std::F64`

Desired frame rate

##### field `encode`

Type: `Std::Option Std::Path`

Enable encoding.

Save the drawing result of each frame to the specified directory.

##### field `verbose`

Type: `Std::Bool`

Show information to the console

##### field `length`

Type: `Std::Option Funim::Time`

Length of the animation

#### Draw

Defined as: `type Draw = Cairo::Cairo -> Std::IO ()`

Type for drawing operations.

#### Time

Defined as: `type Time = Std::F64`

#### TimeDelta

Defined as: `type TimeDelta = Std::F64`

## Traits and aliases

## Trait implementations