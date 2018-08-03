# 2-bit-coin
Extracting 2 bits with every coin toss, with nothing more than one coin and a
sheet of paper.

To ensure 50% probability on the coin either landing on a grid edge or not, the
following JavaScript function can return the grid length of a given diameter:

```javascript
function grid(d) { return(d*(2+Math.sqrt(2))); }
```

## U.S. Coins

* Penny
  - Diameter: 1.905
  - Grid length: 6.504
* Nickel
  - Diameter: 2.121
  - Grid length: 7.2415
* Dime
  - Diameter: 1.791
  - Grid length: 6.1148
* Quarter
  - Diameter: 2.426
  - Grid length: 8.2828
* Half Dollar
  - Diameter: 3.061
  - Grid length: 10.4509
* Dollar (Sacagawea)
  - Diameter: 2.65
  - Grid length: 9.0476

## Canadian Coins

* Penny
  - Diameter: 1.905
  - Grid length: 6.504
* Nickel
  - Diameter: 2.12
  - Grid length: 7.2381
* Dime
  - Diameter: 1.803
  - Grid length: 6.1558
* Quarter
  - Diameter: 2.388
  - Grid length: 8.1531
* 50-cent
  - Diameter: 2.713
  - Grid length: 9.2627
* Loonie
  - Diameter: 2.65
  - Grid length: 9.0476
* Toonie
  - Diameter: 2.8
  - Grid length: 9.5597

## Euro Coins

* 1-cent
  - Diameter: 1.625
  - Grid length: 5.548
* 2-cent
  - Diameter: 1.875
  - Grid length: 6.4016
* 5-cent
  - Diameter: 2.125
  - Grid length: 7.2552
* 10-cent
  - Diameter: 1.975
  - Grid length: 6.743
* 20-cent
  - Diameter: 2.225
  - Grid length: 7.5966
* 50-cent
  - Diameter: 2.425
  - Grid length: 8.2794
* 1 euro
  - Diameter: 2.325
  - Grid length: 7.938
* 2 euro
  - Diameter: 2.575
  - Grid length: 8.7915
