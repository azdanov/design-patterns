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
    - [Adapter](#adapter)
    - [Facade](#facade)
    - [Template Method](#template-method)
    - [Iterator](#iterator)
    - [Composite](#composite)

## Basics

* Abstraction - the quality of dealing with ideas rather than events
* Encapsulation - the action of enclosing something in or as if in a capsule
* Polymorphism - the condition of occurring in several different forms
* Inheritance - the practice of passing on functionality
* Coupling - a term used when two objects are loosely coupled, they can interact, but have very little knowledge of each other.
* Cohesion - a term used as a measure of how closely a class or a module supports a single purpose or responsibility. A module or class has high cohesion when it is designed around a set of related functions, and it has low cohesion when it is designed around a set of unrelated functions.

## Principles

* Identify the aspects of your application that vary and separate them from what stays the same.
* Program to an interface, not a concrete implementation.
* Favor composition over inheritance (Composite reuse principle).
* Strive for loosely coupled designs between objects that interact (Loosely Coupled Principle).
* Classes should be open for extension but closed for modification (Open/closed principle).
* Depend on abstractions. Do not depend on concrete classes (Dependency inversion principle).
  * No variable should hold a reference to a concrete class.
  * No class should derive from a concrete class.
  * No method should override an implemented method of any of its base classes.
* Talk only to your immediate friends (Principle of Least Knowledge).
  * Only invoke methods that belong to:
    * The object itself
    * Objects passed in as a parameter to the method
    * Any object the method creates or instantiates
    * Any components of the object
* Don’t call us, we’ll call you (Hollywood Principle).
* A class should have only one reason to change (Single responsibility principle).

## Patterns

### Strategy

![Strategy](http://www.plantuml.com/plantuml/svg/hLGzJyCm4DtzAqwTKa4N9APAg50X8G5JXmw8uOWlYKLYHxRJKghost4-ciPfsYuTCbZtxjsxz-pCZ4LjYoo5XTLeATumPhw5p55Z1ff2Yp9E2ROCGAj2yhdIaZJStRCTOuVwQ9uAadPK0V7BEBBGGfYYCJ1Fi3ovhh88i8q4fNm7Vql2NCadId0bb8PrTVGXZpfJkaLWUQe16Tb4EKHB7lJPRg7NF9xwhJSh9JX48aviC5pZ597a9ug6h3_oIC79FazOC2JJcGkDVQ-oL0ZqOvsMZfi7n5ByekO32CTYLUocDzvtydgM8UQcI5tc76hXiDSmQe8Iqf5461BqDglBdSqAGpKa65UbIlvUtcAjD6zxHPQdbBcxOYwordvrkAV7vEyOY_2gvCs0KrvLQPsnoazpoAaACMJKMncqtzzPw09nkqz3F-3L2-5gSst-ydDJsE6LJoOFFVTxHM-Ir_cH2Cv9VXuHzD9iWINTsNpOpBq9zt_x1m00 'Strategy')

The Strategy Pattern defines a family of algorithms, encapsulates each one, and makes them interchangeable.
Strategy lets the algorithm vary independently from clients that use it.

---

### Observer

![Observer](http://www.plantuml.com/plantuml/svg/jLH1JiCm4Bpd5NjCLPe-WAegAa8WWK02YRERR1f374Vs9b8Kmjj9sZXrMmTwuMPfPySpisklD355XKZXUQDHbQYyXunGnIn4U2qs7nWIr1v0BP0I6JLGIXw1mYtNBSmq-UO0Sk802rdYHT1C4eyhWz3-n6iyRvqohU4T6IMeRXanu29FKM16-bXZp35jgMOtIh7giLMuC5HBa8RqsaR6gMG4X297nQXGwAWcXU0HfyfHoXLglUkohKp_p0Zg80WQLyzOLESTt-x4e9xFOwcGXSdW6NXMoa-48eyOeJzfZkNklMoHtWuv-2wD0_2-Z-Htr4kVZZ_gLoCz8Uimksdw_JYke4_U7F8zWx2mwuHbMumwCnRjR4Vhn45zbbNJhPUry4FUvnlVHpSkiACoonW4oyDxiXTNpgp2SDlYAmXWNIZLwZLehlEKLIUOktQk8TDagkPjE7kFJKmlSp4sg6ZFEKnoU9OdalxxKc-5MTH-Lpy0 'Observer')

The Observer Pattern defines a one-to-many dependency between objects so that when one object changes state, all its dependents are notified and updated automatically.

---

### Decorator

![Decorator](http://www.plantuml.com/plantuml/svg/nPFFIiGm4CRlVOgXfouhHRqjYx1eFNfHV80q7RkXRR8aKnLAtjr4jzd-SR671MyXcM--Rtv3TeQOfhQf8KEkD2EbeuZbXZJZ1Bncni0zlgDc9K8N0NHl0kl2mWjf8Kieq70j3YIKX3k8NsKbrOU4_2Y9lQ91sYidMVUY4YaxwP8LT6cQsd5fo52eDgyHk3AKh28RHJ-XCgQhPyKC0NuIoc8Qi-yKwhpDDEwZEMWqHiKmSH-PEfr6QhM4TBDnbNP6w479GZGeAK3y8zLWlZDCJfC-YReAxNvn6cubkFKBs8vTVQzaLkGdfBqmQN_Xs8IZNRZ2db4lJ6SbQuYllXF4swMyRwxTO-XuVBO3DehlsSNW-6R_JCT7M8xdzYoUdGFYVlKN 'Decorator')

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

---

### Adapter

![Adapter](http://www.plantuml.com/plantuml/svg/SoWkIImgAStDKN1CIImeIItYuahEIImkLd3EoKpDAr6evghbuihC0qga9IQdAeGa5gMdWaGL5AfpKqioybDg5OfI2qjJYqiqDAr1QY6weOOHgp0LLM5nGMfoPbfcSX2A1gYBzFJieCxWWjcIhuiX1585DPkBoo4rBmNeHG00 'Adapter')

The Adapter Pattern converts the interface of a class into another interface the clients expect. Adapter lets classes work together that couldn’t otherwise because of incompatible interfaces.

### Facade

![Facade](http://www.plantuml.com/plantuml/svg/SoWkIImgAStDKN1BJ4vCIUNYIiv9B2vMSCx9JCqhKQZcgeM9GEGX8b1PNLqxc3QehAwkGd5fKd5bSKbghfv_KbPgSeaX7ZbZBgwynDpKueB4v5I4f0BG4WK5g6wGDWZJ29kWCLpG225eWasbALpG69jACsILG2ywfEQb08C50000 'Facade')

The Facade Pattern provides a unified interface to a set of interfaces in a subsystem. Facade defines a higher-level interface that makes the subsystem easier to use.

### Template Method

![Template](http://www.plantuml.com/plantuml/svg/pLJ1QiCm3BtxAmIxT9U6vhfIEdOklOpT7KTfp1mxEEeObFpxP2SPQnR3Sbj88BBrdfwUZ8yTIK_Nni0hDgsHX4B8eYCl5O4oiklWUGnVOdGJ0BS6gNPb3_lYK6ahpJuh3a0ZmIbkRXwVGkR45NEd8APFmRb5BqaxkriFoKV8eXxbhF98-Al0txBdtBLpxs6f5y8wGl3wKXEuQkRFGuKLAcJa7Jq77qwNYqP5Jo5f22JxXcIFiRgkOhdDe7mg0ybM0NeHla5xUosCLf4XA5yiDL9c6MXk2Hkq5BVMqEHhQGhd34eR1m81t0kq9OIX27x8NTXNz4pAqE48lqcl0wEsEy1FulIbO_rZsEbPf5E-NTnkuTo65Mdu_nurdQAnixcy_3_9u_V8MlXo-080 'Template')

The Template Method Pattern defines the skeleton of an algorithm in a method, deferring some steps to subclasses. Template Method lets subclasses redefine certain steps of an algorithm without changing the algorithm’s structure.

### Iterator

![Iterator](http://www.plantuml.com/plantuml/svg/fP8z3i8m38Ntdi8Z33a1g2fYOk42Y25gJHefFoWn20drxWIQDA6m88OCjlFU-sAbySGTNRI27Q7ZP5rLaHL8FJguLm3IXFw9jmWR8HmAJlZg0xGEGv5aY-KgT8TmMiMzXwsIQEZD85sDUeCt6bK0FVVxedIexHMJvJ13YW7M10B2Z2NrMQ4EgVvNrcWr0HPEVq2FAm36whpS3BPcB2tfyobFpPogAiJiqCkkGtEi9uyObWTPzyM_q7_4D6Ywy2CU 'Iterator')

The Iterator Pattern allows traversal of the elements of an aggregate without exposing the underlying implementation. It also places the task of traversal on the iterator object, not on the aggregate, which simplifies the aggregate interface and implementation, and places the responsibility where it should be.

### Composite

![Composite](http://www.plantuml.com/plantuml/svg/hPA_JiD03CRtUmfBBEdG0KQGKAKi3Bn1nU3UEUIaYrsT3K92UNSkQPEqfLDXl9__VVvy6pNCzj4bgANRYqOZvqpUoLhAyEq0V49Lg5CajlB4dLf6RnCVghY4nbm0sLD6YyBtrUhfd3nC14EevheZozJ99_t2HKVTnXIgU4Izww_gUoLiWBwCEDmYgbyMdMpuGxT_MF7WDwpNpyly6MxR60BnssbiDE0oCfvpsUYycsCfR2Tcqe4q1mll6ch8qoEye08B-45Q9hvCNfhE5RMmOMG512KRacGyafzI5IH3AbFKkKsnjlow7m00 'Composite')

![CompositeTree](http://www.plantuml.com/plantuml/svg/XPFB3i8W44NtynNzWIw4hflws9ZepfrnGNHg6YarGFzV38P7BR0-1xWpDtHACwddaLVxQNnFQj1uaOW04k-QYIV7Qilv6SMigYiu1swXSHW4og-pK1R6KUEuCSe9MRzEIPPIJqECIg7K-UUjamxWEIbmMk3DQiYTHFRgcSh7T5OoQ6IGeX5kpDLOrsthAmDVdWL-dOiZqGpmTyurd2GaIQYvBgWn3FAxCaD9bj8iRG3YQk99xUCbWnGDCr-7uc6-sGS0 'CompositeTree')

The Composite Pattern allows us to build structures of objects in the form of trees that contain both compositions of objects and individual objects as nodes. Using a composite structure, we can apply the same operations over both composites and individual objects. In other words, in most cases we can ignore the differences between compositions of objects and individual objects.
