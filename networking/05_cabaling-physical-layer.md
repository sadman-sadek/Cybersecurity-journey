# Part 2 --- Cabling, Connectors, Media and Physical Networking

# 1. Twisted-pair copper

Twisted-pair cable contains pairs of insulated copper wires twisted
together.

### Why twist the wires?

Twisting reduces electromagnetic interference and crosstalk.

Two major Ethernet cable types:

-   **UTP:** Unshielded Twisted Pair
-   **STP:** Shielded Twisted Pair

### UTP

-   No overall metallic shielding
-   Cheap and flexible
-   Very common in Ethernet LANs

### STP

Uses shielding to reduce interference.

Useful in environments with significant electromagnetic interference.

------------------------------------------------------------------------

# 2. Ethernet cable categories

Common categories:

  -----------------------------------------------------------------------
  Category                            General capability
  ----------------------------------- -----------------------------------
  Cat 5e                              Common Gigabit Ethernet cabling

  Cat 6                               Higher performance and improved
                                      noise characteristics

  Cat 6a                              Designed for 10 Gb/s up to standard
                                      copper Ethernet distance limits

  Cat 7/7a                            Higher-spec shielded cabling
                                      standards; terminology can vary by
                                      deployment
  -----------------------------------------------------------------------

### Important exam principle

Do not choose a cable only by the category number. Consider:

-   Required speed
-   Distance
-   Frequency
-   EMI environment
-   Connector/termination requirements
-   Installation standard

------------------------------------------------------------------------

# 3. Twisted-pair connectors

## RJ45 / 8P8C

Ethernet copper cables commonly use an **8P8C modular connector**,
commonly called RJ45.

### Straight-through

Historically used to connect unlike device types.

Modern Ethernet devices often support **auto-MDI-X**, so the distinction
is less important than it once was.

### Crossover

Historically used to connect similar device types, such as
switch-to-switch or PC-to-PC.

------------------------------------------------------------------------

# 4. Coaxial cable

Coaxial cable has:

1.  Central conductor
2.  Insulating dielectric
3.  Shield
4.  Outer jacket

### Advantages

-   Good shielding
-   Useful over longer distances than some copper designs
-   Used in cable broadband and other RF applications

### Common connectors

-   **BNC**
-   **F-type**
-   Other connectors depending on the RF/network application

------------------------------------------------------------------------

# 5. Fiber-optic cable

Fiber carries data as **light**, not electrical signals.

### Main components

-   Core
-   Cladding
-   Buffer/coating
-   Jacket

### Types

## Single-mode fiber (SMF)

-   Small core
-   Laser-based transmission
-   Long distances
-   High bandwidth

## Multimode fiber (MMF)

-   Larger core
-   Common for shorter distances
-   Often used inside buildings/data centers

### Advantages

-   High bandwidth
-   Long distance
-   Resistant to electromagnetic interference
-   Electrically isolated

### Disadvantages

-   More delicate installation
-   Specialized termination/testing equipment
-   Often more expensive to install

------------------------------------------------------------------------

# 6. Fiber connectors

Common connector families include:

-   **LC:** Small form factor; very common in modern deployments.
-   **SC:** Larger push-pull connector.
-   **ST:** Bayonet-style connector; common in older installations.

### Remember

**LC = Little Connector** is a useful memory aid.

------------------------------------------------------------------------

# 7. Media converter

A **media converter** changes one physical media type into another while
allowing the network connection to continue.

Example:

`Copper Ethernet → Media Converter → Fiber → Media Converter → Copper Ethernet`

### Common use

Connecting copper-based equipment to a fiber backbone.

### Important

A media converter is about **media conversion**, not routing between IP
networks.

------------------------------------------------------------------------

# 8. Cabling tools

Common tools:

## Crimping tool

Attaches modular connectors to compatible copper cable.

## Punch-down tool

Terminates individual wires into patch panels or keystone jacks.

## Cable stripper

Removes the outer jacket/insulation.

## Cable tester

Checks: - Continuity - Wiring order - Shorts - Opens - Other faults
depending on tester

## Toner and probe

Helps identify/trace a particular cable in a bundle.

## Fiber tools

May include: - Fiber cleaver - Fiber stripper - Fusion splicer - Optical
power meter - Visual fault locator

------------------------------------------------------------------------

# 9. Physical-layer troubleshooting logic

If a link is completely down, check from the physical layer upward.

### Basic sequence

1.  Is the device powered?
2.  Is the cable connected?
3.  Are link LEDs active?
4.  Is the correct cable type used?
5.  Is the connector/termination correct?
6.  Test the cable.
7.  Check interface speed/duplex.
8.  Check switch port configuration.
9.  Continue upward to IP/DNS/application testing.

### Key principle

**No physical link → higher-layer troubleshooting may be meaningless.**

------------------------------------------------------------------------

# 10. Quick recall

-   Copper Ethernet → electrical signals.
-   Fiber → light.
-   UTP → no cable shielding.
-   STP → shielding reduces interference.
-   SMF → long distance.
-   MMF → shorter distances, common inside facilities.
-   Media converter → changes media type.
-   Crimper → modular connector termination.
-   Punch-down tool → patch panel/keystone termination.
-   Cable tester → verifies cable wiring/continuity.

## Exam traps

-   Fiber is immune to electromagnetic interference because it carries
    light.
-   A media converter does not automatically mean routing.
-   RJ45 is a common term for Ethernet modular connectors, but
    technically Ethernet commonly uses 8P8C modular connectors.

