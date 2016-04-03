

Apps nowadays are all about fancy **animations**, complex **transitions** and **custom views**, and the user experience must be the most robust and similar as possible in any device. Those patterns gonna help you build an app that's smooth, responsive, and uses as little battery as possible, it covers micro-optimizations that can improve overall app performance.


## General Patterns to avoid bad performance

- Avoid blocking **main Thread**

- Avoid **unnecessary** invalidations that may **trigger** a cascade of invalidations

- Use **RelativeLayouts** in a high hierarchy level

- Avoid Nested **weights** in LinearLayouts ( Cz each child needs to be measured twice)

- Avoid Customs **views** not **properly** made

- Avoid Creating **Unnecessary** Objects

- Use **Static Final** For Constants (static 15%-20% faster)

- Primitives (Integer vs Float 2x slower)

- Avoid Internal **Getters/Setters** (direct field access 3x faster)

- Use Enhanced For **Loop** Syntax

- Consider **Package** Instead of Private Access with Private Inner Classes

- Use **Native** Methods Carefully

## Patterns for custom views
  
Keep It as Simple as Possible (KISS)

- Use **<merge>** tag as root in your layout (avoid extra ViewGroups on inflation)

- **<include>** tag (easy code reuse of common layouts)

- Avoid **unnecessary** layouts

- Don’t make allocations or heavy operations in **OnDraw**

- Remove unnecessary calls to **invalidate()**

- Consider creating your own ViewGroup 

- RecyclerView (replaces ListView and GridView)

## Patterns to avoid memory churn

- Don’t allocate a large amount of **unnecessary** objects:
	
	- Immutable classes: String
	
	- Autoboxing: Integer, Boolean…
	
	- Don’t allocate in onDraw

- Consider using **Object Pools** and caches to reduce churn

- Be mindful of the overhead of enums (a single reference to an enum constant occupy **4 bytes**)

## Patterns to avoid memory leaks 

- Don't leak **contexts** in inner classes

- Don't leak **views** inside activity

- Favor **static** inner classes over **non static**

- Don't use **WeakHashmap** as cache. Only the keys are **WeakReference**
 
## Patterns for CPU

- Do not nest **multi-pass** layouts

- Lazily compute complex data when needed

- Cache **heavy** computational results for **re-use**

- Consider **RenderScript** for performance

- Keep work **off** of the **main thread**

##  Patterns to avoid Overdraw

- Simplify your **drawables**

- Use **nine patch** with transparent parts

- Caution with setting **alpha** in your views

## Patterns to handling Bitmaps

Handle bitmaps in a poper way:

- Decode **bitmaps** to the desire size: **BitmapFactory.Options** (inSampleSize, inDensity, inTargetDensity)
  
- Load bitmaps in **memory** at the dimensions is going to be displayed

- Don’t **scale** if you don’t need to (**createScaledBitmap(btimap, int, int)**)

- Use **LRU** cache

## Patterns for I/O

- Batch operations with reasonable **back-off** policies

- Use **gzip** or **binary** serialization format

- Cache **data** offline with **TTLs** for reloading

- Use **JobScheduler API** to batch across OS

## Patterns for Services

- Do not keep running **service** unless it's actively **performing** a job. Also be careful to **stop** service it when its work is done

- System prefers to always keep the service process in running. Then the RAM used by the service can’t be used by anything else or paged out

- The best way to limit the lifespan of your service is to use an IntentService, which finishes itself as soon as it's done handling the intent that started it

- Leaving a service running when it’s not needed is one of the worst memory management mistakes an Android app can make

## Patterns for Threads

- In a Thread **run()** method use **Process.setThreadPriority()** with **THREAD_PRIORITY_BACKGROUND**. This approach reduces resource competition between the Runnable object's thread and the **UI thread**.

- If you don't set the thread to a **lower priority** this way, then the thread could still slow down your app because it operates at the **same priority** as the **UI thread** by default.

- **Stores** the current **Thread** reference in your app, so that you want to interrupt the Thread later on. e.g On network failure you can cancel that thread operation.

## Patterns to avoid ARNs

- On **UI thread** do as little work as possible

- If your application is doing work in the background in response to user input, show that progress is being made (such as with a ProgressBar in your UI).

- Use performance tools such as **Systrace** and **Traceview** to determine bottlenecks in your app's responsiveness.

- If your application has a **time-consuming** initial setup phase, consider showing a **launch screen** or **rendering** the main view as quickly as possible, indicate that loading is in progress and fill the information asynchronously.

**links & Ressources:**

- http://billynyh.github.io/tech-talks/google-android-performance-1.html
- http://developer.android.com/training/best-performance.html
- http://developer.android.com/training/articles/perf-tips.html

