# FRP-6: Survey Existing Auction Literature

**Fellow:** @sbaks0820
</br> **Contributors:** 
</br> **Status:** In Progress
</br> **Type:** Survey
</br> **Updated:** 18.11.2020

**Simple summary:** 
</br> A survey of ad auctions, other priority auctions games and computational game theory papers.
This is a survey of existing auction techniques and the beginning of a longer process of developing mempool auction theory.

**Motivation:**
</br> We have built sealed-bid block space auction mechanism for communicating transaction order preference. 
We don't thint this mechanism is optimal or ideal and would like to refine it.

**Proposed deliverable:**
</br> 
* Survey of existing techniques, why they are or are not appropriate to use
* Develop early thoughts around mempool auction theory?
* Regarding the POC version of the bundle auction (see last point in resources below): @jparyani brought up that the divisor means that the bundle auction favors small bundles. The full impact of this design are not currently known and would benefit from further study.

**Proposed Approach:**
</br> Looking at the assumptions of existing techniques might disqualify subsets of them, for example the auctions where there is a no-collusion assumption from the auctioneer.
</br> It might be helpful to try to enumerate the assumptions that we can make for bidders in our context. 
Things such as budget constraints, participation in repeated games. I arrived at this paper from another RTB paper I was reading: http://wnzhang.net/share/rtb-papers/repeat-auction.pdf. 
It introduces this idea of Fluid Mean Field Equilibrium, which is a computationally feasible alternative to Bayesian equilibrium, for repeated auctions. 
It also makes some specific assumptions about bidders valuing each auction equally and their budget constraints. It think it could be promising direction.

**Resources:**
* https://arxiv.org/pdf/1901.06830.pdf
* https://arxiv.org/pdf/1610.03013.pdf
* http://wnzhang.net/share/rtb-papers/repeat-auction.pdf
* http://dosamobile.com/wp-content/uploads/2017/08/TwoAlternatives.pdf
* https://www.cs.cmu.edu/~sandholm/cs15-892F13/algorithmic-game-theory.pdf (Chapter 11 on Combinatorial Auctions)

* Here is the POC version of the bundle auction: Flashbots miners select the most valuable bundle per unit of gas used and place it at the beginning of the list of transactions included in a block at the given blockheight. Miners determine the value of a bundle based on the following equation where the change in block.coinbase balance represents a direct transfer of ETH through a smart contract.
![Alt Text](https://user-images.githubusercontent.com/15959632/99228128-7c883b00-27ec-11eb-8b95-3896b21e0b08.png)