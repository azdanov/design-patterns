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
      - ["Simple Factory"](#simple-factory)
      - [Factory Method](#factory-method)
      - [Abstract Factory](#abstract-factory)
    - [Singleton](#singleton)
    - [Command](#command)

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

#### "Simple Factory"

![Factory Simple](http://www.plantuml.com/plantuml/svg/ZPBB2i8m44Nt-OfPAb9_G11149T2mNrennfeap2TuYFqtqsRgX7QuYeXzypZpcHNioHkgX8ECcD33qXLPKiK8YjbNSD9FPyozGA24m3keh3CMqW6h9VVaPTmRZpt3LjCWykET1NorVYKgn04XdAa_hf8cPGkW1yMb-08kI4DjfFQZMY5Y9epIR8TwIb6rkjjA256Mkh4_HMnnbdaXDOY6QrcgJCMXPfFT9GtgPJKyzLwSTZ42EFY-ONfPOIIyR_nXRoHQy0xeyw7hVlq7-ZNzpGNEP-6VhoFOMBdN_oVV040 'Factory Simple')

"Simple Factory", while not a design pattern, is a simple way to decouple your clients from concrete classes.

#### Factory Method

![Factory Method](http://www.plantuml.com/plantuml/svg/jLEzQiCm4Dxr50TTsYKFq4095Bor13nbLEtFjQXY6UcIDZ5-zqfM11QrAHqwIlVzdj3EiRHyEcegPCN6NkW5t9fQ2FdcsFexghHqZlRgUfKqY548qHa6MVNUCfacJahF1TqrQ53XaIeBoPWczm-a72MroDLeLgd6rh29-Qcq9jMTpGTopULyKMeGH4CQZxVa6NiR4CUfw4Xde-hCTHjAplGscwSeugj7izV3R8mlHbV_J93q5_nfiE2JxQWFvt4oJCebNpJsw7jOqwb8pYpY8sJmvnPmMCLcSKERHPTLs4mz-PR5VosWBFwqW1lybmLaSKEpHPTLMBQ0dHVt_-KR 'Factory Method')

The Factory Method Pattern defines an interface for creating an object, but lets subclasses decide which class to instantiate. Factory Method lets a class defer instantiation to subclasses.

#### Abstract Factory

![Factory Abstract](http://www.plantuml.com/plantuml/svg/lLJ1QiCm3BthAtJSBls1mMXfAUomCTfUTjGSBJ4aph2TGnlwxqjbGsnAavnsa-Id9-b9UEqyMTyrDUv9-TQUSVFjl1ri08eMgfgSmqzzkH3sS0Nu-1BdE2GmhbQluUtDb9OBpSP7hdjS32n0YWkFy08vLTfiRUVyhktAQXfxuBBKPDfjnUnu6ljELXkoTAHEpK13bn04ocRe0R5ls5TjSOtIASlaMUodvvURZjfujZ-a-860mYBJnMInRyc8qbqCYnt2OS0O3quibZLvNqetlpKtGy3zHpEJgYxOvv8zXlt1RA7vClD5naq6XVfHyVnCKvqJw9WVDKi8yjjD2LBio12MaH1a1vtc9qXOioc6V-0F 'Factory Abstract')

The Abstract Factory Pattern provides an interface for creating families of related or dependent objects without specifying their concrete classes.

---

### Singleton

![Singleton](http://www.plantuml.com/plantuml/svg/ZP51YiCm34NtFeLWDWb3smCa3TtEQXPpWiQH4u6hJ1sPBeBlNiKGqa8BtTdoU_yZV9ha72HUFFmHznvbP6FzUPgsEym6O7Q4lakmWxfjr16ozQ5j7gYQciXqZVZ3-iuMwmCrbL5tjr552NFAm--tGJtA6h7X-ptyoe01BYZ3s4qwCCaO7WKXK3y8ZEuXuykXGuigQij_R3rP-AHCXQoGorpnSYau7XU6e_SBjMe0R-WCu-svkIYhRAMrCg34m1bw3bcuP90xMBOr9ptfVzq1 'Singleton')

The Singleton Pattern ensures a class has only one instance, and provides a global point of access to it.

---

### Command

![Command](http://www.plantuml.com/plantuml/svg/hPDDImCn48Rl-HK3lQnWwrtBKkn9A2YzU10F-p5nGvDCsSmMeVI_E_lHbMqeKl2MOPwyR_9EiWgSrTmu2sjoBlEbKeNDGe0jEcBSK5PY3KTrKbvAODh3J6lz26jhqFEKNfFdcgpW04Tjq9Qdi-p79oppbFnGXkL3dZvTnRIEE8TSaO01UUWbGXhFBG714j_3A2_BKU9kiftySyDC_ZqBRqseC5AvmBN-cu-oUV47sc6jb81Owwp0y_twQCxg-8r5mvXq6aEI6_DLyHGZdqIdIdvzBMeUZBTOe3cqpjE1q3mTvpiPx6AHzewgzrtEgQzVn_oYZhzuAHSy6BUtwEHnX1jlFIhVAD6ba9ECoKaqqNbc6hNa8ljbTFicjwRefYVLWKpPhKV1pgSZRIlJDXT3t00dXQBNsbqnzV_dwMFBbIpbf_u0 'Command')

The Command Pattern encapsulates a request as an object, thereby letting you parameterize other objects with different requests, queue or log requests, and support undoable operations.
