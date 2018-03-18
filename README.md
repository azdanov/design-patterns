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
    - [Decorator](#decorator)
    - [Factory](#factory)
      - [Method Factory](#method-factory)
      - [Abstract Factory](#abstract-factory)

## Basics

* Abstraction - the quality of dealing with ideas rather than events
* Encapsulation - the action of enclosing something in or as if in a capsule
* Polymorphism - the condition of occurring in several different forms
* Inheritance - the practice of passing on functionality

## Principles

* Identify the aspects of your application that vary and separate them from what stays the same.
* Program to an interface, not a concrete implementation.
* Favor composition over inheritance.
* Strive for loosely coupled designs between objects that interact.
* Classes should be open for extension but closed for modification.
* Depend on abstractions. Do not depend on concrete classes.
  * No variable should hold a reference to a concrete class.
  * No class should derive from a concrete class.
  * No method should override an implemented method of any of its base classes.

## Patterns

### Strategy

![Strategy](http://www.plantuml.com/plantuml/svg/hLBDJiCm3BxdANpiXE0DG1CS4QSTTZQDsrfgaYdnLY0gpqv2H9TL4rmu9PQ_7t-Mjq7Goz6Ci1EFGlsxmjUGlgr0Es88y3HWhiX3L02nOnhr39zxmeEpZpJWYPs7wRlC04Cok8HOUCqQke5Ou70FqrnpRawEDNJS3z8igBjZe2BHRAwW0ycbmLz-ir8bsRFDHa1lGbPNGN_wU_v0hw_rsQQdmvPWvHNh-QgvpwQxoNczuDaSHZ9a9VogL99MUX0hPiYIPMji-ohW2_RS_g-NoPANNkS3SRSFAscbjcbtwRo-0000 'Strategy')

The Strategy Pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable.
Strategy lets the algorithm vary independently from clients that use it.

---

### Observer

![Observer](http://www.plantuml.com/plantuml/svg/jLH1JiCm4Bpd5NjCLPe-WAegAa8WWK02YRERR1f374Vs9b8Kmjj9sZXrMmTwuMPfPySpisklD355XKZXUQDHbQYyXunGnIn4U2qs7nWIr1v0BP0I6JLGIXw1mYtNBSmq-UO0Sk802rdYHT1C4eyhWz3-n6iyRvqohU4T6IMeRXanu29FKM16-bXZp35jgMOtIh7giLMuC5HBa8RqsaR6gMG4X297nQXGwAWcXU0HfyfHoXLglUkohKp_p0Zg80WQLyzOLESTt-x4e9xFOwcGXSdW6NXMoa-48eyOeJzfZkNklMoHtWuv-2wD0_2-Z-Htr4kVZZ_gLoCz8Uimksdw_JYke4_U7F8zWx2mwuHbMumwCnRjR4Vhn45zbbNJhPUry4FUvnlVHpSkiACoonW4oyDxiXTNpgp2SDlYAmXWNIZLwZLehlEKLIUOktQk8TDagkPjE7kFJKmlSp4sg6ZFEKnoU9OdalxxKc-5MTH-Lpy0 'Observer')

The Observer Pattern defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

---

### Decorator

![Decorator](http://www.plantuml.com/plantuml/svg/nPF1JeGm48RlVOe99pQhZNhRR3GRnQCNZGzGO8G6Q3Vje2Q4TxViBbrWtIm74s-adN_-Vxuf6ql2K5sL466YZI1j61En9ICIWgGKri8ZVg8H6KB309eFYMNQmXiPgJ98qIP6Rabg1VSGlAj2wIy5yK4IT8eAATTEikn56L9qr8KBQ3ZdxRZKPqXr7PS8YROKBbZBs3vK94pngeKbm6z2bKvZzfryNMSpZVjijmQjrG5Ct4UcJcUGQgE0hrQkiZqXzAHLAYjKv25UI3MOxmoJuwGliYnykr-SXblnRlq2rcFNhbTuKjHDIBcql3zmRFndEtE5FQDUo4zAbX1SxH84wxcyRs_SfUzuk6u7R7IIYp-3qpNxPpfTXFbuxixYsJqQVVtWXsPxLACZjd7OtB__0m00 'Decorator')

```java
// Example usage of decorator pattern
Beverage beverage = new DarkRoast();
beverage = new Mocha(beverage);
beverage = new Milk(beverage);
System.out.println(beverage.getDescription() + " $" + beverage.cost());
// Output: Dark Roast Coffee, Mocha, Milk $1.29
```

The Decorator Pattern attaches additional responsibilities to an object dynamically. Decorators provide a flexible alternative to subclassing for extending functionality.

---

### Factory

#### Method Factory

![Factory Method](http://www.plantuml.com/plantuml/svg/jLEzQiCm4Dxr50TTsYKFq4095Bor13nbLEtFjQXY6UcIDZ5-zqfM11QrAHqwIlVzdj3EiRHyEcegPCN6NkW5t9fQ2FdcsFexghHqZlRgUfKqY548qHa6MVNUCfacJahF1TqrQ53XaIeBoPWczm-a72MroDLeLgd6rh29-Qcq9jMTpGTopULyKMeGH4CQZxVa6NiR4CUfw4Xde-hCTHjAplGscwSeugj7izV3R8mlHbV_J93q5_nfiE2JxQWFvt4oJCebNpJsw7jOqwb8pYpY8sJmvnPmMCLcSKERHPTLs4mz-PR5VosWBFwqW1lybmLaSKEpHPTLMBQ0dHVt_-KR 'Factory Method')

The Factory Method Pattern defines an interface for creating an object, but lets subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.

#### Abstract Factory

![Factory Abstract](http://www.plantuml.com/plantuml/svg/lLF1QiCm3BtxAtJSBls1mMZf6EomCTfUTjGSBJ4aph2LGnlwxqjbGMnAkvvwUvAVdfvaUnaP0mzT2wzekGzxM7r73XCs1XM1RJ56-7I70y9eZiPyV4cmdGe85eldTFRcwq2L8y-gTSxJn0rC2Sqblb1sZVFhC4H-wOUwkSxTK5qxzFsw8OfqdVkEmNaCkCN1_aDDBarQK373Q036ZhZfgwEkpWP29i4FZq-dFJhF57xGqeK5YefCfyM2JyK0uaxJWbCw3QZv56YpmkHvAzVzjjHDYNWFC_FaIN6S7PRNcllAg7EzziW4ohlE1NBkh93CPmB50yZhCwPPag-cV_C7 'Factory Abstract')

The Abstract Factory Pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes.
