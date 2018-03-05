# Design Patterns

A set of common object-oriented ideas that help solve common programming challenges.

## Table Of Contents

- [Design Patterns](#design-patterns)
  - [Table Of Contents](#table-of-contents)
  - [Basics](#basics)
  - [Principles](#principles)
  - [Patterns](#patterns)
    - [Strategy](#strategy)
    - [Observer](#observer)

## Basics

* Abstraction - the quality of dealing with ideas rather than events
* Encapsulation - the action of enclosing something in or as if in a capsule
* Polymorphism - the condition of occurring in several different forms
* Inheritance - the practice of passing on functionality

## Principles

1.  Identify the aspects of your application that vary and separate them from what stays the same.
2.  Program to an interface, not a concrete implementation.
3.  Favor composition over inheritance.
4.  Strive for loosely coupled designs between objects that interact.

## Patterns

### Strategy

![Strategy](http://www.plantuml.com/plantuml/svg/hP8nRiCm34LtdOAZWoAzGO6W7OjE6J8p5cqJiAH0Ok8cXdlsIXNYo47GBfqaWO__an_Q144lHzF3LZmAjMU5-n2ljK3TOmZmrc5waOTH0OmDKwyd-DeH7fnzfGvFx3mCFyy469BEHMBkg-xH5OmPXnSOfhBdwUHOGyDj9zLCFHy3PObgzO0E94k3l_mcfMuxkVKQbhnIUUztcyO0-XIokeZXMj_n1Rr-L6SRZmPhkbFE0LwdBxPA8sNHxU2yddasXvuCMGc_AkKS2ZqOYywG97EcRDlfvlM1BTV_wsMIvD9h4zE9t-iR 'Strategy')

The strategy pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable.
Strategy lets the algorithm vary independently from clients that use it.

---

### Observer

![Observer](http://www.plantuml.com/plantuml/svg/jLJ1JeD04Btp5NEagT2xDaPJOpJHQAA9voqxm5fWoUv0GX2_tQMmbBPKU_6sOT-yVU_D33UQcA8YJU1bhL6Lg9p7Z525B41uAzQV613K3a2T8iMIDr1AmK5X9BI1sIBN7a3E9i2fBF4iQ2P9X9L5Q7VcD8wpIfZMy86CObHtZ1Y8D4ymnOpqliPGO6Ael5kbMFLa52ujrJL8IterHeQ9P0I4QOwAKQ5muZOkKi45LHDNkKAjjrLZA_C_CuBQz_rcgkPKLCSLtzE9GRrOX58X2-B1CuYib1k48kUCq9qr-t8xBn7I-ou7TqhZ07pe8_aTzTgduvxqgv6UaRMORJVTlXqNq2Tl3td7a8wmgvXb4VBMp8ZMsz9Eug0-ogffnyjEaFIytHACjc1eml4Qz7cULjto3_NBBz-7LQ6KaMMdMUWyOPLZb27831AHRIw1Tr-Dv40M2OSrci4mMiYqbGCpGq-cIHXL1zptvZvWcYohNPt9D_VjpC_pSwgFEyKTODZQ0qd__QXpWnatVxCV 'Observer')

The observer pattern defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.
