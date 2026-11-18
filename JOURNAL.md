# GyroLock development journal

## nov 17, 2026 — initial setup

started working on GyroLock for Hack Club Forge :D

the idea is to build a 3-axis active stabilization system that keeps an inner platform pointing in the same direction even when the outer frame gets rotated or tilted.

basically, i want to make something that you can pick up, move around, and mess with while the inside tries its absolute hardest to not give a shit about what the outside is doing. (yes, this is word for word in README. sue me. i dare you.)

### what i did

- created the initial project directory and organized it into `cad/`, `electronics/`, `firmware/`, and `images/`
- set up the README with the project goals, planned hardware, and development roadmap
- started looking into how gyroscopes, motorized gimbals, and active stabilization systems work
- decided to aim for 3-axis stabilization, starting with a simpler single-axis prototype

### initial design decisions

im planning to use a motorized gimbal rather than relying entirely on a spinning gyroscope.

the idea is to measure orientation using an IMU, then use a microcontroller to calculate motor corrections.

the motors should counteract changes in the outer frame's orientation so that the inner platform stays relatively stable.

some things i still need to figure out:

- what motors have enough torque without being ridiculously heavy
- which IMU to use
- how to arrange the three rotational axes
- how to prevent wires from getting twisted
- what control algorithm to use
- how to power everything without making it enormous

### problems / concerns

the biggest concern right now is mechanical design.

a 3-axis gimbal sounds pretty straightforward until you realize that all three axes need to move without interfering with each other. (yes this is also paraphrased. again, mail all complaints to the chicago municipital paper shredding dept.)

also, i need to account for sensor drift and motor response times.

if the controller is tuned badly, the whole thing could start oscillating like a washing machine having a fucking seizure.

I would prefer to avoid that and keep my hand in the general shape of a hand and not a mangled blob of flesh.

### next steps

1. research motor and IMU options
2. sketch the mechanical layout
3. start the first CAD model
4. estimate torque requirements
5. choose components for a single-axis prototype

### current status

planning and project setup. no physical prototype yet.

hopefully this thing eventually works instead of becoming an extremely expensive paperweight.

:D

## nov 18, i have too much fucking free time :3 (coming soon, but yes i have a ish free day tmrw so expect some progress)
