# dev/

This folder is a **reference catalog, not a loaded part of the extension**.
`_extension.yml` does not reference anything under `dev/`, and no consuming
project should add `dev/class_library.scss` to its own `theme:` list.

## Why this exists

Three sibling AU course-book repos (STAT-427-627, DATA-413-613, DATA-793
`lectures_book`) each maintain their own project-specific `scss_<course-code>.scss`
file, loaded after `brand`/`brand-overrides*.scss` in `_quarto.yml`. Over time,
useful classes get invented in one book and are easy to forget existed by the
time a different book needs the same thing. `class_library.scss` is the fix:
a single, well-commented catalog of every class known to be useful across
these books, kept here so it updates alongside the brand itself.

## Using it

Open `class_library.scss`, find the class you want, and copy it into your
project's own `scss_<course-code>.scss`. It's fine for a project to carry a
class it isn't using yet — the cost of an unused rule is low, and it saves
re-deriving the same fix (e.g. the Mermaid dark-mode scoping fix, or the
`.img-light-bg` dark-mode wrapper) from scratch later.

## Contributing back

If you invent a new generically-useful class in a consuming book, add it here
too (with the same kind of "why this exists" comment used throughout the
file) so the next book gets it for free.
