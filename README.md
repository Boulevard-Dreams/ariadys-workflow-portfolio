# Ariadys workflow portfolio

Four n8n workflows I built and run for my own outbound system. None is client work. This repo describes what each one does and what it does not do. It holds no workflow files, credentials or account IDs.

## Email finder: five lookups in order

Finds a business email for a company. It tries a company search first, then three domain searches, then scrapes the About page and has a language model pull a name, then runs a finder on that name, then verifies the result. First version May 2026, reshaped over about three months. On a 25-lead test it found emails for 16, with a median machine time of 71.7 seconds.

## Reply sorter: rules, not AI

Reads replies and sorts them with keyword and regex rules in a single Code node. The order is noise, opt-out, negative, then "send". It is not AI classification. Built July 2026. It ran 320 inbox checks in 18.6 seconds.

## Error alert

An n8n Error Trigger that posts a Discord message when a workflow fails: two nodes. It does not catch every failure. Nodes set to continue on error swallow their failures before they reach it. Built July 2026.

## Daily sheet backup

Exports five sheets and a suppression list to a private GitHub repository every day. Built August 2026. Median run 15.2 seconds.

## Contact

Open to small n8n and Make fixes and builds through Upwork.
