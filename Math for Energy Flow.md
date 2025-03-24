About the math involved in energy flow computations.

You only get a few pieces of information from the Envoy.
  * Solar production
  * Home load consumption
  * Grid in / out
  * Battery in / out

From these, we figure out where the energy is coming from & going to.

The analysis I do is in terms of sources and drains, or producers and consumers, if you will.

First, Solar is always a producer (or off), while the Home load is always a consumer (or off, I suppose).&nbsp;
While the Grid & Battery are either producers or consumers (or off), but of course, the Grid is never both producer & consumer simultaneously, and the same goes for the Battery.

Next, we do an analysis of the count of producers (and the count of consumers).&nbsp; The possible values are:
  * 3 producers (Solar, Battery, Grid)
     * This means there can only be 1 consumer (the Home load) and so the analysis for this case is fairly simple given the information we get.&nbsp; The Home load is consuming from all three sources,
        and we know the energy flows rather directly from the measurements.
  * 2 producers
  * 1 producer
    * The analysis of this case is also simple: the Home load is being powered by one of the possible producers; just figure out which one and we know the flow also rather directly.

The other cases involve 2 producers and either 1 or 2 consumers.&nbsp; When only 1 consumer, the situation is also fairly straightforward, we know that the energy is flowing from those 2 producers to the consumer.

When there are 2 producers and 2 consumers, we can’t really be sure how much of each producer’s energy is flowing to each of the 2 consumers individually.&nbsp; The approach here is to make a rational argument toward bookkeeping of where the energy is coming & going, as follows:

For one 2/2 case, if Grid & Solar are producers then Battery & Home load are consumers, so we argue that Solar is  charging the battery to the fullest extent possible.&nbsp; In other words, we consider that all possible solar is going to charging, and only excess solar is going to the Home load.&nbsp; Therefore, any Grid draw is going to the Home load, and then if there’s any leftover, that’s going to the Battery.&nbsp; It is a bookkeeping solution, but also how the Enphase system is designed (to charge from Solar as priority rather than charge from the Grid — this means that battery power is “clean” in that it has been produced from the sun, rather than from the Grid).

For the other 2/2 case, if Solar & Battery are producers, then Grid & Home load are consumers.&nbsp; Again, we choose as bookkeeping, that all possible Solar is feeding back into the Grid, while all possible Battery is powering the Home load.

Alternate bookkeeping / accounting is possible, but in the end, without more detailed measurements we cannot really know for sure whose energy is going where, and, I'm not even sure we could make a measurement here
as there's a pool of energy produced by more than 1 producer being consumed by more than 1 consumer.&nbsp; 
However, we can infer from the design of the system of (a) to charge battery from solar and (b) to send solar back to the grid as preference over sending battery to the grid
that solar and battery are being used appropriately.
