# Source Floorplan

Open [the offline map](index.html) after downloading it. GitHub may show HTML source rather than execute it. Use **Start here**, **Flows**, search and the details-panel toggle to read the architecture. On narrow screens the fit-to-view overview can be small; readable details/tour prose is the preferred path.

A terminal books catalog imports suggested titles into SQLite, adds or lists books, edits/deletes a selected ID and reports catalog statistics. No HTTP routes.

## Source boundary

CSV seed records and runtime database are outside the admitted graph. This is a CLI, not Flask despite app.py naming. Input parsing, empty-catalog analysis and dependency compatibility are not runtime-qualified.

Pinned original source: `6d03f8edebd32fbf35406c58bc80f4ad16b45bbe`. Original project licensing is unchanged. See [notices](NOTICE.md), [omissions](source-census.json), [authoring](architecture.json) and [integrity pins](source-manifest.json). This is source documentation, not application execution, secure deployment approval or automatic refresh.

## Check without running the application

```sh
python3 docs/floorplan/check_freshness.py
python3 -B -m unittest discover -s docs/floorplan/tests -v
python3 -B -O -m unittest discover -s docs/floorplan/tests -v
```

The checker compares original source/config/static/input-file hashes and file membership, and all reviewed map artifacts. It does not regenerate on drift. Tests create disposable copies, never import the application, and require only Python standard library and Git. Regeneration requires a separately qualified renderer and reviewed authoring; its runtime is not bundled here.
