# provide Scala Functions to Java8 lambda implicit conversions

### Caution

* require Scala 2.11.0-M3 or higher <http://www.scala-lang.org/downloads>
* current version sbt(0.12.4 or 0.13.0) [does not support java8](https://github.com/sbt/sbt/issues/842)

### Example

```scala
Welcome to Scala version 2.11.0-M3 (Java HotSpot(TM) 64-Bit Server VM, Java 1.8.0-ea).
Type in expressions to have them evaluated.
Type :help for more information.

scala> :load Scala2Java8.scala
Loading Scala2Java8.scala...
import java.util.function._
import scala.language.implicitConversions
defined trait Scala2Java8
defined object Scala2Java8
warning: previously defined trait Scala2Java8 is not a companion to object Scala2Java8.
Companions must be defined together; you may wish to use :paste mode for this.

scala> import Scala2Java8._
import Scala2Java8._

scala> java.util.stream.IntStream.iterate(0,{(_: Int) + 1})
res0: java.util.stream.IntStream = java.util.stream.IntPipeline$Head@5b080f3a

scala> res0.map{(_: Int) * 2}
res1: java.util.stream.IntStream = java.util.stream.IntPipeline$3@4a067c25

scala> res1.limit(10).toArray
res2: Array[Int] = Array(0, 2, 4, 6, 8, 10, 12, 14, 16, 18)
```

### License
public domain

### TODO
* implicit priority
* provide Java8 lambda => Scala Functions

