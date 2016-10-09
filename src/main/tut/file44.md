```tut:book
import shapeless._

case class Foo(
  a: Int,
  b: Int,
  c: Int,
  d: Int,
  e: Int,
  f: Int,
  g: Int,
  h: Int,
  i: Int,
  j: Int,
  k: Int,
  l: Int,
  m: Int,
  n: Int,
  o: Int,
  p: Int,
  q: Int,
  r: Int,
  s: Int,
  t: Int)

object Foo {
  val generic = Generic[Foo]
}
```
