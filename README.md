# Embargo Economy SMP Plugin Blueprint

A high-stakes, strategic SMP game loop built for Skript. The gameplay revolves around earning points to anonymously ban items globally, creating structural constraints and server-wide manhunts without artificially inflating survival difficulty.

---

## 1. Core Economy & Points System
The plugin utilizes a dual-layer banking system to balance player risk with asset security.

* **Virtual Points (Unsecured):** A digital balance tied directly to the player's account. These are liquid, spendable instantly at the spawn Altar, but vulnerable to PvP theft.
* **Physical Tokens (Secured):** Players can visit the Altar to withdraw their virtual points into physical items (Altar Tokens). Once converted, they can be securely stored in an Ender Chest or traded with teammates. They cannot be spent until deposited back into the Altar.

### Crafting Recipe
Players who focus on building or grinding can generate points safely through heavy resource investment:
* **Ingredients:** 4 Netherite Scraps + 4 Echo Shards + 1 Diamond Block
* **Output:** 1 Physical Altar Token (Contains custom NBT data/lore to prevent Anvil renaming exploits).

---

## 2. Kill & Death Mechanics
* **Player Kills:** Eliminating an opponent automatically awards the killer +2 Virtual Points.
* **PvP Death Penalty:** If a player is killed by another player, they lose 30% of their current Virtual Balance. Any physical Altar Tokens carried in their active inventory drop on the ground as loot.
* **Environmental Death:** Dying to mobs, lava, or fall damage does not penalize a player's virtual point balance.
* **The Reset Condition:** If a player who currently has active item bans running is killed by another player, all of their active global bans are instantly broken and lifted.

---

## 3. The Spawn Altar & Banning Loop
Located at the world spawn is a physical Altar interface. Interaction triggers a curated selection process:

* **The Selection Cost:** Players spend 5 points for a Common Ban pool roll or 15 points for a Rare Ban pool roll.
* **The RNG Rule:** The Altar generates 3 random available items from the chosen tier. The player has up to 2 rerolls to cycle the selection.
* **The Anonymity Factor:** When an item is selected, a global server broadcast announces what item has been banned. The identity of the player who enacted the ban remains entirely hidden.
* **The Restriction:** For as long as an item is banned, all click, hold, craft, or use events associated with that item material are canceled globally.

### Curated Item Pools
* **Common Tier (5 Points):** Ender Pearls, Shields, Water Buckets, Bows/Crossbows, Iron Chestplates, Golden Carrots.
* **Rare Tier (15 Points):** Totems of Undying, Enchanted Golden Apples, Elytras, Netherite Ingots/Scraps, Obsidian, Splash Potions of Healing II.

---

## 4. Custom Weapons Meta

### Altar's Edge
* **Acquisition:** Crafted using 4 Altar Tokens + 1 Netherite Sword base.
* **Ability:** Grants a 25% chance to double point gains on a player kill (+4 points instead of +2).
* **Risk:** If a player dies while holding this weapon, a server-wide chat message exposes their name and list of active bans, permanently destroying their anonymity.

### Greed Blade
* **Acquisition:** Crafted using high-tier materials or purchased via Altar milestone.
* **Ability:** Deals +0.5 extra attack damage for every 2 virtual points currently sitting unspent in the attacker's virtual balance.
* **Risk:** Damage scaling is capped at a maximum bonus of +4.0 (2 hearts). To maintain maximum lethality, the player must run the high-risk strategy of hoarding points instead of banking them as physical tokens.
