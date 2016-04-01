
Apps nowadays are all about fancy **animations**, complex **transitions** and **custom views** And the experience must be the most robust and similar as possible in any device 

## Patterns to avoid bad performance

A lot of frame drops? Check for:

- Unnecessary invalidations that may trigger a cascade of invalidations.(GPU View Updates can help profiling)

- RelativeLayouts in a high hierarchy level

- Nested weights in LinearLayouts

- Unnecessary overdraw

- Customs views not properly made

##  Patterns to follow when you have too much overdraw

- Simplify your drawables

- Use 9patch with transparent parts

- Caution with setting alpha in your views

## Patterns for custom views
  
Keep It as Simple as Possible (KISS)

- Use <merge> as root in your layout

- Avoid unnecessary layouts

- Don’t make allocations or heavy operations in OnDraw

- Remove unnecessary calls to invalidate()

- Consider creating your own ViewGroup 

## Patterns to avoid memory churn

- Don’t allocate a large amount of unnecessary objects:
	
	- Immutable classes: String
	
	- Autoboxing: Integer, Boolean…
	
	- Don’t allocate in onDraw

- Consider using Object Pools

## Patterns to avoid memory leaks 

- Don't leak contexts in inner classes

- Don't leak views inside activity

- Don't use WeakHashmap as cache. Only the keys are weak references 
 
## Patterns for CPU

- Do not nest multi-pass layouts

- Lazily compute complex data when needed

- Cache heavy computational results for re-use

- Consider RenderScript for performance

- Keep work off of the main thread

## Patterns to handling Bitmaps

Handle bitmaps in a poper way:

- Decode bitmaps to the desire size: BitmapFactory.Options (inSampleSize, inDensity, inTargetDensity)
  
- Load bitmaps in memory at the dimensions is going to be displayed

- Don’t scale if you don’t need to (createScaledBitmap(btimap, int, int)

- Use LRU cache

## Patterns for Memory

- Use object pools and caches to reduce churn

- Be mindful of the overhead of enums

- Do not allocate inside the draw path

- Use specialized collections instead of JDK collections when appropriate (SparseArray)

## Patterns for I/O

- Batch operations with reasonable back-off policies

- Use gzip or binary serialization format

- Cache data offline with TTLs for reloading

- Use JobScheduler API to batch across OS
