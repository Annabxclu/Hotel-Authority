# Hotel Authority

A browser-based hotel management simulator. You run the hotel through a management dashboard of lists, tables, profiles and reports. There are no 3D graphics or animated characters.

## Play

Open `index.html` in any modern browser. It is a single self-contained file with no build step.

## What's in this prototype

- **Setup:** hotel name, Sandbox or Career mode, starting budget and starting rating. Every hotel starts with 2 floors, 3 guest rooms, a reception, a restaurant and 9 staff.
- **Game clock:** 1 real second = 1 game minute at 1×. Pause, 1×, 2× and 4× speeds. The clock pauses when the tab is hidden.
- **Reservations:** requests are generated automatically. The player accepts, declines or offers another room. Overlapping bookings are blocked, and confirmed guests who never arrive become no-shows.
- **Manual check-in:** a checklist validates the room (vacant, clean, big enough, dates valid). If the room isn't ready, the player can reassign it. Walk-in guests leave if they wait too long.
- **Manual checkout:** guests become *Checkout Due* at 11:00 on their departure day and keep their room until the player checks them out. Itemised bill, then confirm payment, then complete checkout. Stays can be extended.
- **Housekeeping:** tasks are created automatically. Assign them manually or turn on auto-assign. Cleaning time depends on room type, condition and staff skill. Rooms go through cleaning and inspection before they're available again.
- **Guests:** permanent IDs, 8 personalities, preferences, budgets, activity simulation, spending history, requests, complaints, reviews and past stays.
- **Operations:** floors, rooms (8 categories), room upgrades, in-room extras, 12 facility types, restaurant menu, opening hours and stock, room service and guest requests, personnel (hire, fire, shifts, training), marketing campaigns.
- **Finance and reports:** permanent transaction history, daily, weekly and monthly summaries, pricing controls, occupancy, ADR, RevPAR and rating trends.
- **Career mode:** 7 objectives with rewards and unlocks, plus achievements. Buying floors is never locked behind a level.
- **Saving:** automatic, to browser storage (and to the player's account when run as a Claude artifact). Save codes can be exported and imported. Only one tab runs the simulation at a time.

## Roadmap

The target stack is Next.js, React, TypeScript, PostgreSQL, Prisma and Tailwind, with a server-authoritative simulation.

1. Scaffold Next.js + Prisma + Postgres with accounts.
2. Move the simulation (`stepMinute`, reservations, check-in/out, housekeeping, finance) into server-side modules with a tick loop per online hotel.
3. Put money, reservations and room assignments inside database transactions. Add an exclusion constraint so a room can't be booked twice for the same dates.
4. Rebuild the dashboard screens as React components.
