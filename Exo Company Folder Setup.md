The architecture is solid. A few things to sharpen it and one real pushback:

  What's exactly right:

  - Deliverable as the atomic unit — not step, not task. The output is the thing.

  - skill.md lives with the deliverable, not the workflow. Composability only works this way.

  - Workflow orchestrates, skill executes. That's a clean separation.

  - The ~150 line rule is a good forcing function.

  Three things to add:

  1. Name deliverables as nouns (outputs), not verbs (actions)

  04-generate-exocare-agreement/ → 04-exocare-agreement-draft/

  05-send-for-esign/ → 05-agreement-sent-for-signature/

  The workflow becomes a sequence of states rather than a to-do list. This matters when an agent is deciding "what exists right now and what's missing."

  

  2. The workflow README needs typed handoffs — not just sequence

  

  Deliverable 3 → inputs: {client_email, plan_tier}

                  produces: {pandadoc_doc_id, doc_url}

  

  Deliverable 4 → inputs: {pandadoc_doc_id}

                  produces: {signed_pdf_url, signed_at}

  

  This makes the workflow machine-readable. An agent can inspect the state of any deliverable and know what's unblocked next. Without this, orchestration is still implicit.

  

  3. executor: field in deliverable frontmatter

  

  executor: ai | human | client | hybrid

  

  One line. Immediately tells you the maturity level of that deliverable and who's blocking the workflow right now.

  

  ---

  The pushback:

  

  Scripts and tools need a distinction. His model has scripts/ at the deliverable level — good for deliverable-specific logic. But the PandaDoc API config, Airtable schemas,

  Telegram creds — those are infrastructure, not deliverable-specific. If 8 deliverables across 3 workflows all call PandaDoc, you don't want 8 copies of the connection setup.

  The clean split:

  

  departments/legal/

  ├── tools/esign/          ← infrastructure: API setup, auth, schemas

  └── workflows/

      └── exocare-enrollment/

          └── 04-agreement-draft/

              ├── skill.md

              └── scripts/

                  └── generate.py    ← calls tools/esign/ — doesn't re-implement it

  

  Deliverable scripts are callers of department-level tools. Tools are the infrastructure layer. That's the boundary.

  

  ---

  What the full structure looks like:

  

  Department

    └── tools/              ← infrastructure: APIs, schemas, credentials setup

    └── workflows/

          └── [workflow-name]/

                ├── README.md               ← trigger, sequence map, typed handoffs, stress test, "role this replaces"

                └── [##-deliverable-name]/

                      ├── skill.md          ← frontmatter: executor, inputs, output, tools-used

                      ├── references/       ← templates, examples, copy, standards

                      └── scripts/          ← automation code that calls department tools/

  

  ---

  One open question before we rebuild:

  

  The existing departments/README.md defines the old format. Do you want to update that file to make this the new canonical standard — so every future department and every

  agent session knows the correct architecture from the start? That should probably happen before we migrate the 3 workflows, so there's a spec to build against.