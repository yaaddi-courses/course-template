# Yaaddi Course Template

Click **"Use this template"** above to start a new Yaaddi flashcard course
under the [yaaddi-courses](https://github.com/yaaddi-courses) organization.

## Getting started

1. Create your new repo from this template (name it after your course, e.g.
   `yaaddi-courses/my-new-course`).
2. Fill in `source/meta.csv`, `source/units.csv`, `source/cards.csv` — see
   [AUTHORING.md](AUTHORING.md) for the full card-writing guide and format
   reference.
3. Update `meta.json` (title, description, cover image, tags).
4. Add a cover image and any card images under `source/images/`.
5. Build and validate locally:
   ```bash
   python validate_course.py . --source
   python build_course_zip.py .
   ```
6. Commit the built `.zip` (it's meant to be tracked, not gitignored — see
   AUTHORING.md for why) and open a PR. The repo's own
   `.github/workflows/validate-course.yml` runs the same validation
   automatically.
7. Once merged, **tag your new repo with the `yaaddi-course` topic**
   (Settings → General → Topics, or `gh repo edit --add-topic yaaddi-course`)
   — this is the ONLY manual step that makes the course show up in the app's
   Course Library. The [yaaddi-courses/yaaddi-courses](https://github.com/yaaddi-courses/yaaddi-courses)
   catalog repo scans the org for this topic on a schedule (and can be
   triggered manually) to rebuild `catalog.json`.

## What's in this template

- `source/` — a minimal working skeleton (one deck, one card) so you start
  from something valid, not an empty file.
- `meta.json` — course metadata.
- `AUTHORING.md` — the full authoring guide: card types, structure rules,
  word/prompt-length limits, and everything `validate_course.py` checks for.
- `build_course_zip.py` / `validate_course.py` / `ensure_course_ids.py` —
  the standard Yaaddi course tooling, scoped to this one repo (no sibling
  courses to scan — each course is its own repo now).
- `tools/generate_language_course.py` (+ its test) and
  `tools/check_word_coverage.py` — extra tooling for building/checking a
  language-learning course specifically (base-language-framed vocabulary
  courses). Not needed for a non-language course.
- `.github/workflows/validate-course.yml` — runs `ensure_course_ids.py` +
  `validate_course.py . --source` on every push/PR.

## License

Course content in repos created from this template is licensed under
[PolyForm Noncommercial 1.0.0](LICENSE) unless you choose otherwise.
