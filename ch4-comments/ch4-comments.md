# /* _Comments_ */
 
## Table of Contents

* [Good Comments](#Good-Comments)
* [Bad Comments](#Bad-Comments)
* [References](#References)
---
## Good Comments
---

## Bad Comments

### Mumbling
 His mumbling left behind an _enigma_
```java
public void loadProperties()
   {
     try
     {
      String propertiesPath = propertiesLocation +
       ”/” + PROPERTIES_FILE;
      FileInputStream propertiesStream = new
       FileInputStream(propertiesPath);
      loadedProperties.load(propertiesStream);
     }
     catch(IOException e)
     {
       // No properties files means all defaults are loaded
     }
   }

```
### Redundant Comments
> If comments are not inforamtives, add no value to your code, just remove them.

 The comment probably takes longer to read than the code itself.
```java
 // Utility method that returns when this.closed       is true.  Throws an exception   // if the timeout is reached.

 public synchronized void waitForClose(final long timeoutMillis)  throws Exception   {     
      if(!closed)      {       
       wait(timeoutMillis);
      if(!closed)
      throw new Exception("MockResponseSender could not be closed");      }

```

### Misleading Comments
> Code never lies, comments do sometimes

> Comments should desribe what your code **actualy** do, but not what you **wish** your code to do.
```java


### Mandated Comments
> Do not add a comment for each function or  variable. If they do not need commenting, leave them uncommented.

/**
    * 
    * @param title The title of the CD
    * @param author The author of the CD
    * @param tracks The number of tracks on the CD
    * @param durationInMinutes The duration of the CD in minutes
    */
   public void addCD(String title, String author, 
                      int tracks, int durationInMinutes) {
     CD cd = new CD();
     cd.title = title;
     cd.author = author;
     cd.tracks = tracks;
     cd.duration = duration;
     cdList.add(cd);
   }

```
### Journal Commnets
>  Adding a log-like comment isn't a good idea.<br> ⚠ Hey, we have version control now!

```java

 * Changes (from 11-Oct-2001)
 * --------------------------
 * 11-Oct-2001 : Re-organised the class and moved it to new package 
 *               com.jrefinery.date (DG);
 * 05-Nov-2001 : Added a getDescription() method, and eliminated NotableDate 
 *               class (DG);
 * 12-Nov-2001 : IBD requires setDescription() method, now that NotableDate 
 *               class is gone (DG);  Changed getPreviousDayOfWeek(), 
 *               getFollowingDayOfWeek() and getNearestDayOfWeek() to correct 
 
 *               bugs (DG);
 * 05-Dec-2001 : Fixed bug in SpreadsheetDate class (DG);
 * 29-May-2002 : Moved the month constants into a separate interface 
 *               (MonthConstants) (DG);
 * 27-Aug-2002 : Fixed bug in addMonths() method, thanks to N???levka Petr (DG);
 * 03-Oct-2002 : Fixed errors reported by Checkstyle (DG);
 * 13-Mar-2003 : Implemented Serializable (DG);
 * 29-May-2003 : Fixed bug in addMonths method (DG);
 * 04-Sep-2003 : Implemented Comparable.  Updated the isInRange javadocs (DG);
 * 05-Jan-2005 : Fixed bug in addYears() method (1096282) (DG);
```


### Noise Comments
* Stating the Obvious
```javascript
// Avoid Monkey Patches from Application Insights// Avoid Monkey Patches from Application Insights
bootstrap.avoidMonkeyPatchFromAppInsights();
// Enable portable support
bootstrap.configurePortable();
// Enable ASAR support
bootstrap.enableASARSupport();
// Load CLI through AMD loader
require('./bootstrap-amd').load('vs/code/node/cli');

```

### Scary Noise Comments

```java
   /** The name. */
   private String name;

   /** The version. */
   private String version;

   /** The licenceName. */
   private String licenceName;

   /** The version. */
   private String info;

```
### HTML Comments
> HTML in source code comments is an abomination.
> It makes the comments hard to read in the one place where they should be easy to
read.
```java
/**
* Task to run fit tests.
* This task runs fitnesse tests and publishes the results.
* <p/>
* <pre>
* Usage:
* &lt;taskdef name=&quot;execute-fitnesse-tests&quot;
* classname=&quot;fitnesse.ant.ExecuteFitnesseTestsTask&quot;
* classpathref=&quot;classpath&quot; /&gt;
* OR
* &lt;taskdef classpathref=&quot;classpath&quot;
* resource=&quot;tasks.properties&quot; /&gt;
* <p/>
* &lt;execute-fitnesse-tests
* suitepage=&quot;FitNesse.SuiteAcceptanceTests&quot;
* fitnesseport=&quot;8082&quot;
* resultsdir=&quot;${results.dir}&quot;
* resultshtmlpage=&quot;fit-results.html&quot;
* classpathref=&quot;classpath&quot; /&gt;
* </
```

### Nonlocal Information
If you must write a comment, then make sure it describes the code it appears near. Don’t
offer systemwide information in the context of a local comment.
```java
/**
* Port on which fitnesse would run. Defaults to <b>8082</b>.
*
* @param fitnessePort
*/
public void setFitnessePort(int fitnessePort)
{
this.fitnessePort = fitnessePort;
}
```

### Too Much Information
Don’t put interesting historical discussions or irrelevant descriptions of details into your
comments.

```java
/*
RFC 2045 - Multipurpose Internet Mail Extensions (MIME)
Part One: Format of Internet Message Bodies
section 6.8. Base64 Content-Transfer-Encoding
The encoding process represents 24-bit groups of input bits as output
strings of 4 encoded characters. Proceeding from left to right, a
24-bit input group is formed by concatenating 3 8-bit input groups.
These 24 bits are then treated as 4 concatenated 6-bit groups, each
of which is translated into a single digit in the base64 alphabet.
When encoding a bit stream via the base64 encoding, the bit stream
must be presumed to be ordered with the most-significant-bit first.
That is, the first bit in the stream will be the high-order bit in
the first 8-bit byte, and the eighth bit will be the low-order bit in
the first 8-bit byte, and so on.
*/
```

### Inobvious Connection
The connection between a comment and the code it describes should be obvious.
> You’d like the reader to be able to look at the comment and the code and understand what the comment is talking about.
```java
/*
* start with an array that is big enough to hold all the pixels
* (plus filter bytes), and an extra 200 bytes for header info
*/
this.pngBytes = new byte[((this.width + 1) * this.height * 3) + 200];
```

### Function Headers
Short functions don’t need much description. A well-chosen name for a small function that
does one thing is usually better than a comment header.

### Java docs in non public code
> As useful as javadocs are for public APIs, they are anathema to code that is not intended
for public consumption
* Bad Comment example
```java
/**
* This class Generates prime numbers up to a user specified
* maximum. The algorithm used is the Sieve of Eratosthenes.
* <p>
* Eratosthenes of Cyrene, b. c. 276 BC, Cyrene, Libya --
* d. c. 194, Alexandria. The first man to calculate the
* circumference of the Earth. Also known for working on
* calendars with leap years and ran the library at Alexandria.
* <p>
* The algorithm is quite simple. Given an array of integers
* starting at 2. Cross out all multiples of 2. Find the next
* uncrossed integer, and cross out all of its multiples.
* Repeat untilyou have passed the square root of the maximum
* value.
*
* @author Alphonse
* @version 13 Feb 2002 atp
*/
import java.util.*;
public class GeneratePrimes
{
/**
* @param maxValue is the generation limit.
*/
public static int[] generatePrimes(int maxValue)
{
if (maxValue >= 2) // the only valid case
{
// declarations
int s = maxValue + 1; // size of array
boolean[] f = new boolean[s];
int i;
// initialize array to true.
for (i = 0; i < s; i++)
f[i] = true;
// get rid of known non-primes
f[0] = f[1] = false;
// sieve
int j;
for (i = 2; i < Math.sqrt(s) + 1; i++)
{
if (f[i]) // if i is uncrossed, cross its multiples.
{
for (j = 2 * i; j < s; j += i)
f[j] = false; // multiple is not prime
}
}
// how many primes are there?
int count = 0;
for (i = 0; i < s; i++)
{
if (f[i])
count++; // bump count.
}
int[] primes = new int[count];
// move the primes into the result
for (i = 0, j = 0; i < s; i++)
{
if (f[i]) // if prime
primes[j++] = i;
}
return primes; // return the primes
}
else // maxValue < 2
return new int[0]; // return null array if bad input.
}
}

```
* Refactored code
```java
/**
* This class Generates prime numbers up to a user specified
* maximum. The algorithm used is the Sieve of Eratosthenes.
* Given an array of integers starting at 2:
* Find the first uncrossed integer, and cross out all its
* multiples. Repeat until there are no more multiples
* in the array.
*/
public class PrimeGenerator
{
private static boolean[] crossedOut;
private static int[] result;
public static int[] generatePrimes(int maxValue)
{
if (maxValue < 2)
return new int[0];
else
{
uncrossIntegersUpTo(maxValue);
crossOutMultiples();
putUncrossedIntegersIntoResult();
return result;
}
}
private static void uncrossIntegersUpTo(int maxValue)
{
crossedOut = new boolean[maxValue + 1];
for (int i = 2; i < crossedOut.length; i++)
crossedOut[i] = false;
}
private static void crossOutMultiples()
{
int limit = determineIterationLimit();
for (int i = 2; i <= limit; i++)
if (notCrossed(i))
crossOutMultiplesOf(i);
}
private static int determineIterationLimit()
{
// Every multiple in the array has a prime factor that
// is less than or equal to the root of the array size,
// so we don't have to cross out multiples of numbers
// larger than that root.
double iterationLimit = Math.sqrt(crossedOut.length);
return (int) iterationLimit;
}
private static void crossOutMultiplesOf(int i)
{
for (int multiple = 2*i;
multiple < crossedOut.length;
multiple += i)
crossedOut[multiple] = true;
}
```

---

## References
* Clean Code - ch4
* [Five code comments you should stop writing // and one you should start](https://www.freecodecamp.org/news/5-comments-you-should-stop-writing-and-1-you-should-start-4d66a367cd2c/)
* [Comments In Your Code](https://medium.com/better-programming/comments-in-your-code-730cfd1dde02)
* [Clean Code – Comments and Formatting](https://www.todaysoftmag.com/article/1120/clean-code-comments-and-formatting)
* [Clean Code Slides](https://www.slideshare.net/arturoherrero/clean-code-8036914)
