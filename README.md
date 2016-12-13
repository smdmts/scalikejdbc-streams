# ScalikeJDBC-streams

[![Release](https://jitpack.io/v/yoskhdia/scalikejdbc-streams.svg)](https://jitpack.io/#yoskhdia/scalikejdbc-streams)

It is assumed to be used in batch application.
In JDBC, you need to keep connections constantly while subscribing to streaming. Therefore, please reconsider the connection pool setting and always be careful not to exhaust the connection.


## Getting Started

supports Scala 2.11.x, 2.12.x

```
resolvers += "jitpack" at "https://jitpack.io"
libraryDependencies += "com.github.yoskhdia" %% "scalikejdbc-streams" % <<check the latest version from jitpack.>>
```

## Example

```scala
import scalikejdbc._
import scalikejdbc.streams._

val publisher = DB stream {
  sql"select id from users".map(r => r.int("id")).cursor
}
publisher.subscribe(???)
```
