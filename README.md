# GyroLock

a 3-axis active stabilization thingy that tries to keep its orientation even when you rotate or tilt the outer frame.

im building this for Hack Club Forge because i thought it'd be cool to make something that you can spin around while the inside just... refuses to give a shit about what the outside is doing :D

the idea is to use an IMU, motors, and a microcontroller to measure orientation and actively correct for movement in real time.

still very early in development. currently figuring out how the hell im actually gonna build this.

## what it should do

- maintain the orientation of an inner platform while the outer frame moves
- stabilize across 3 rotational axes (pitch, roll, and yaw)
- use an IMU to measure orientation and angular velocity
- use feedback control to calculate motor corrections
- have a button to lock the current orientation
- run off a battery so it doesnt need to be plugged in
- have a custom 3D-printed frame and motor mounts
- ideally not shake itself to death when the motors start correcting stuff

hopefully it'll be small enough to hold in one hand, but that depends on the motors and battery.

## how it works (hopefully)

the basic idea is a motorized gimbal.

an IMU measures how the device is moving, and a microcontroller uses that information to calculate how the motors should respond.

the motors rotate the inner platform relative to the outer frame, trying to cancel out changes in orientation.

basically, you move the outside and the inside tries its absolute hardest to stay pointed in the same direction.

sounds simple until you realize that sensors drift, motors have limits, and control algorithms can make everything oscillate like a pissed-off washing machine.

also, this isn't some magical anti-gravity bullshit. the whole device can still move around. it's the inner platform that's being stabilized.

## planned hardware

nothing finalized yet, but probably something along these lines:

| component | purpose |
| --------- | ------- |
| ESP32 or similar microcontroller | runs the stabilization code |
| 6-axis or 9-axis IMU | measures orientation and angular velocity |
| 3 motors | control the gimbal axes |
| motor drivers | control the motors |
| battery + power circuitry | portable power |
| 3D-printed gimbal frame | holds everything together |
| bearings and mounting hardware | lets the axes rotate without everything grinding itself to death |
| button / switch | locks orientation and controls power |

exact components will be picked after figuring out the mechanical design, torque requirements, and power consumption.

im not buying random motors and praying they work. probably.

## development plan

1. research stabilization methods and pick components
2. design the first gimbal frame in CAD
3. build a single-axis prototype
4. read IMU data and estimate orientation
5. implement basic feedback control
6. test stabilization and tune the controller
7. expand to 2 axes, then 3
8. add battery power and an orientation-lock button
9. test how well it handles different movements
10. clean everything up and make a final enclosure

the plan will probably change once i start actually building stuff because engineering loves ruining perfectly good plans.

## project structure

```text
GyroLock/
├── cad/             # 3d models and mechanical designs
├── electronics/     # wiring diagrams, schematics, etc
├── firmware/        # microcontroller code
├── images/          # photos, renders, and test results
├── JOURNAL.md       # development logs for Forge
└── README.md        # you are here
```

## testing

once the prototype works, i want to measure how well it maintains its orientation rather than just saying "looks stable enough" and calling it a day.

some things to test:

- angular error while rotating the outer frame
- how quickly the platform recovers after a disturbance
- maximum rotation speed it can compensate for
- motor response and power consumption
- how much sensor drift screws things up over time

ideally i'll record the data and make some graphs comparing the requested orientation against the actual orientation.

because if the thing starts violently shaking itself apart, i'd like to know WHY before it does it again.

## current status

**planning / early design**

the project structure is set up, but the hardware design, component selection, and firmware are still being worked on.

no physical prototype yet.

so right now it's mostly an idea, some folders, and an unreasonable amount of confidence.

## limitations

a few things worth mentioning:

- stabilization is limited by motor torque and speed
- the gimbal has a limited range of motion unless the design supports continuous rotation
- IMU measurements aren't perfect, especially over long periods
- fast movements and impacts can exceed what the system can correct
- battery life will depend on the final motors and electronics
- dropping it on concrete is probably a pretty fucking terrible idea

this is an experimental project, not a commercial camera stabilizer.

## credits

made by **Jnaor** for [Hack Club Forge](https://forge.hackclub.com/).

CAD, electronics, firmware, and testing will be documented as the project progresses.

if it works, cool.

if it doesnt, at least the Git history will be entertaining.

:D
