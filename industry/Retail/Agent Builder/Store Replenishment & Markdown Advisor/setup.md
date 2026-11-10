# Setup: Store Replenishment & Markdown Advisor

This guide takes about 20 minutes. It covers creating the agent, adding the knowledge sources, and running the test prompts.

Before you start, read the [README](./README.md) to see the scenario and the expected results.

---

## Before You Begin

- Access to Agent Builder in Microsoft 365 Copilot.
- The demo knowledge source package: `industry/Retail/Agent Builder/data files/Store Replenishment Demo Pack`.
- Permission to create and share agents in your tenant.

The package contains:

| File | Purpose |
|------|---------|
| `inventory_snapshot.csv` | Stock on hand, weekly sales, weeks of cover, on-order units, and stock flag for each store and SKU (32 rows) |
| `products.csv` | SKU, product name, category, retail price and unit cost (8 SKUs) |
| `stores.csv` | Store ID, name and region (4 stores in 2 regions) |
| `supplier_lead_times.csv` | Supplier, lead time and on-time reliability for each SKU |
| `promotions.csv` | Promotions, their weeks, discount, stores and status |
| `markdown_policy.md` | Stock flags, transfer rules, markdown caps, lead-time rules, and approval rules |

---

## Step 1: Create the Agent

1. Open Agent Builder in Microsoft 365 Copilot.
2. Select **Create an agent**.
3. Enter the name: **Store Replenishment & Markdown Advisor**.
4. Enter the description from the [README](./README.md#description).

---

## Step 2: Add the Instructions

1. Open the **Instructions** section of the agent.
2. Copy the text under **Instructions** in the [README](./README.md#instructions) and paste it in.
3. Save.

Keep the instructions as they are for the demo. Changing a rule (for example, the 4.0-week transfer threshold) changes the expected results in the README.

---

## Step 3: Add the Started Prompts

Add the three started prompts from the [README](./README.md#started-prompts):

- Weekly Stock Health
- Transfer Options
- Delivery Gaps

---

## Step 4: Upload the Knowledge Sources

1. Open the **Knowledge** section.
2. Upload all six files from `Store Replenishment Demo Pack`.
3. Wait for indexing to finish before you test.

**Tip:** Upload the `.csv` files and the `.md` policy together. The agent needs the policy to apply the markdown caps and transfer rules.

---

## Step 5: Test the Agent

Run the demo prompt from the [README](./README.md#demo-prompt), then check each row in the expected results table:

| Check | Pass when |
|-------|-----------|
| Pine Street mug stockout | The agent recommends a Harbor Central transfer and notes the 2025-06-16 delivery |
| Pine Street water bottle | The agent notes the 2025-06-18 delivery gap and does not recommend a Harbor Central transfer |
| Hillcrest cutting board | The agent recommends a Riverside transfer or an expedite |
| Cross-region transfers | The agent never recommends a Metro North transfer to Coastal East, or the reverse |
| Trail Runner Shoe at Harbor Central | The agent finds no same-region transfer and applies the markdown caps |
| Data date | The agent states the 2025-06-06 snapshot date and asks for manager confirmation |

If a check fails, go to the troubleshooting section below.

---

## Step 6: Share the Agent

1. Share the agent with the demo group only. Keep it inside your tenant.
2. Remind testers that the data is fictional and the output is a recommendation for human review.

---

## Troubleshooting

| Problem | What to check |
|---------|---------------|
| The agent quotes numbers that are not in the files | Confirm all six files finished indexing. Ask the agent which file it used. |
| The agent recommends a cross-region transfer | Check that `stores.csv` is uploaded and that the Instructions block is complete. |
| The agent gives a markdown without citing the policy | Check that `markdown_policy.md` is uploaded and that the policy name is in the instructions. |
| The agent does not mention the snapshot date | Check that `inventory_snapshot.csv` is uploaded. Re-ask with "What is the snapshot date?" |
| Answers are vague | Use the demo prompt in the README. Broad prompts give broad answers. |
| The agent says the data is stale | This is correct behaviour if the snapshot is more than 7 days old. The demo snapshot is dated 2025-06-06. Update the date in the snapshot file for a live run. |

---

## Notes for Adapting to Your Business

- Replace the sample files with exports from your own stock system, but keep the same column names.
- Update `markdown_policy.md` with your approved rules. The agent applies only what the file says.
- Keep a human approval step for every markdown, transfer, or delivery change.
