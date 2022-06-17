# todoist-shortcuts changelog

## Version 152

### Fixes ###

* Has `o` / `O` fallback attempt to add task to current section before
  falling back on quick add. See [#211][].


## Version 151

### Fixes ###

* Fixes `o` / `O` bindings for adding tasks before / after.  This was
  due to a bug in todoist-shortcuts (Oops!). See [#211][].

* Fixes `t` for scheduling in task view (may have only been broken
  when experimental features on, not sure, not bothering to check).


## Version 150

### Fixes ###

* Fixes adding a subtask in task view mode. See [#209][].

* Fixes `g` project navigation tags for projects that have sub-projects.

* Fixes behavior of `shift-g` to navigate to current task's
  project. Previously it did not select the correct task after
  navigate (I believe due to changes in todoist URLs).

* Fixes `1`/`2`/`3`/`4` bindings for changing task priority (broken
  due to Todoist changes in HTML structure). See recent discussion on
  [#207].

* Fixes use of `a` to add tasks in grouped agenda views (today /
  upcoming). May fix other cases too. See [#211][].

[#209]: https://github.com/mgsloan/todoist-shortcuts/issues/209
[#211]: https://github.com/mgsloan/todoist-shortcuts/issues/211


## Version 149

### Fixes ###

* Fixes keyboard shortcuts for new task view, no longer falls back to
  native keybindings. See [#204][].

* Fixes cursor motion when a task is present in multiple sections.
  For example, before this fix, if the cursor is on the second
  instance of such a task then pressing down would instead move the
  cursor to the task below the first instance.


## Version 148

### Fixes ###

* Reinstates keybindings for current task view (removed in version
  147).  Uses Todoist native keybindings in new experimental task
  view, because current DOM generated for it uses obfuscated IDs and
  so it is challenging to reliably manipulate it. See
  [#204][].


## Version 147

### Fixes ###

* Fixes keyboard use when task view is open by instead using Todoist
  native shortcuts. This also allows for deletion of some code! See
  [#204][].

* Fixes `~` / `shift-~` shortcuts for rotating between top sections.

* Fixes `c` shortcut for opening comments (broken by redesigned task
  view)

[#204]: https://github.com/mgsloan/todoist-shortcuts/issues/204


## Version 146

### Fixes ###

* Fixes `a` / `shift-a` (add to bottom / add to top) in projects with
  sections. See [recent comment on #93][].

[recent comment on #93]: https://github.com/mgsloan/todoist-shortcuts/issues/93#issuecomment-1127833290


## Version 145

### Fixes ###

* Fixes priority setting shortcuts (`1` / `2` / `3`/ `4`). See
  [#207][].

[#207]: https://github.com/mgsloan/todoist-shortcuts/issues/207


## Version 144

### Fixes ###

* Fixes navigation mode links in the presence of leading emoji. See
  [#206][].

[#206]: https://github.com/mgsloan/todoist-shortcuts/issues/206


## Version 143

### Enhancements ###

* Makes task copying shortcuts handle multiple selected tasks. See
  [#201][].

[#201]: https://github.com/mgsloan/todoist-shortcuts/issues/201


## Version 142

### Fixes ###

* Another attempt to fix bug with navigation mode reported in [a
  comment on #194][].

* Fixes task movement on Firefox when page is scrolled, thanks to
  [matejdro][] for identifying a fix. See [#176][].

[#176]: https://github.com/mgsloan/todoist-shortcuts/issues/176
[matejdro]: https://github.com/matejdro


## Version 141

### Enhancements ###

* Adds `alt+t` keybinding for opening time prompt. See [#198][].

### Fixes ###

* Attempts to fix bug with navigation mode reported in [a comment on
  #194][].

[a comment on #194]: https://github.com/mgsloan/todoist-shortcuts/issues/194#issuecomment-1019452067
[#198]: https://github.com/mgsloan/todoist-shortcuts/issues/198


## Version 140

### Fixes ###

* Attempts to fix missing navigation keys for "Team Inbox". See
  [#194][].

[#194]: https://github.com/mgsloan/todoist-shortcuts/issues/194


## Version 139

### Enhancements ###

* Shortcuts for copying info about current task to clipboard. See
  [#189][].

    * `ctrl+c` - copy title and url of task in markdown format
    * `ctrl+,` - copy task title
    * `ctrl+shift+,` - copy task url

* Adds `ctrl+shift+/` shortcut for opening a random task. See
  [#190][].

* No longer includes minified mousetrap code, as Mozilla is now
  enforcing non minified code policies.

### Fixes ###

* Attempts to fix issue with blurring scheduler text input on
  safari. See [#191][].

[#189]: https://github.com/mgsloan/todoist-shortcuts/issues/189
[#190]: https://github.com/mgsloan/todoist-shortcuts/issues/190
[#191]: https://github.com/mgsloan/todoist-shortcuts/issues/191


## Version 138

### Enhancements ###

* Adds support for `ctrl+k` to open Todoist's command pallete. See
  [#186][].

### Fixes ###

* Fixes keyboard handling when modal dialogs are visible (broken by
  changes to how the dialogs work).

* Makes Todoist's "active item" style use a transparent background, so
  that the todoist-shortcuts cursor is still visible.

[#186]: https://github.com/mgsloan/todoist-shortcuts/issues/186


## Version 137

### Fixes ###

* Fixes behavior of `o` / `O` in sorted projects. Also makes sorting
  keybindings toggle sort enablement. See [llinfeng][]'s [comment on
  #183][].

[llinfeng]: https://github.com/llinfeng
[comment on #183]: https://github.com/mgsloan/todoist-shortcuts/issues/183#issuecomment-959861962


## Version 136

### Fixes ###

* Fixes `p` (sort by priority) to sort in descending order.


## Version 135

### Fixes ###

* The hasty fix for [#184][] did indeed break some shortcuts that
  relied on fallthrough to Todoist native shortcuts. Specifically,
  this fixes `q` (quick add), `m` (toggle left nav), `p` (sort by
  priority), `n` (sort by name), `r` (sort by assignee), and `f` / `/`
  (focus search) by directly implementing these via simulating
  mouseclicks (like the rest of todoist-shortcuts).


## Version 134

### Fixes ###

* No longer calls Todoist's keyhandlers as a fallback. This started
  causing total non-functionality with update to Todoist version 1447.
  I no longer recall why the fallback was in place, so I imagine this
  might break some shortcuts that relied on fallback. See [#184][].

[#184]: https://github.com/mgsloan/todoist-shortcuts/issues/184



## Version 133

### Enhancements ###

* Scheduler now will respond to the number keys, and schedule for `N`
  days after today, where `N` is the number pressed. This addition
  contributed by [Adam Rich][] in [#181][].

[Adam Rich]: https://github.com/adamleerich
[#181]: https://github.com/mgsloan/todoist-shortcuts/pull/181

### Fixes ###

* Inspired by the change in [#181][], the `w` scheduler keybinding for
  "schedule next week" (monday) now works again, despite Todoist no
  longer having a "schedule next week" option.


## Version 132

### Fixes ###

* Fixes setting background color of navigation tips in Chrome and
  probably Opera too.


## Version 131

### Fixes ###

* Fixes `ctrl+s` shortcut for sync. See [#178][].

[#178]: https://github.com/mgsloan/todoist-shortcuts/issues/178


## Version 130

### Enhancements ###

* Removes support for smart scheduler, which was removed from Todoist. See [#179][]

[#179]: https://github.com/mgsloan/todoist-shortcuts/issues/179


## Version 129

### Enhancements ###

* Adds `!` keybinding to open notifications. See [#177][].

### Fixes ###

* Fixes backtick and `~` shortcuts for cycling through inbox / today /
  upcoming / favorites. Probably broken for a long time.

[#177]: https://github.com/mgsloan/todoist-shortcuts/issues/177


## Version 128

### Fixes ###

* Reinstates the bulk move / bulk reschedule features which were
  disabled as part of [#137][].

* Fixes a bug where the number of tasks associated with a favorited
  section affected the choice of keys in navigation mode.

* Fixes `s` for sorting by date. See [#137][] / [#142][].

* Various code cleanups.


## Version 127

### Fixes ###

* Fixes navigation to favorites. See [#173][].

[#173]: https://github.com/mgsloan/todoist-shortcuts/issues/173


## Version 126

### Enhancements ###

* `shift-g` in filter view now navigates to the task's project rather
  than bringing up the "upcoming" view.


## Version 125

### Bug fixes ###

* Fixes a few breakages of `shift-g` shortcut (navigate to task's
  project, or to agenda mode). See [#169][], [#170][], and [#171][].

[#169]: https://github.com/mgsloan/todoist-shortcuts/issues/169
[#170]: https://github.com/mgsloan/todoist-shortcuts/issues/170
[#171]: https://github.com/mgsloan/todoist-shortcuts/issues/171


## Version 124

### Enhancements ###

* No user-facing changes. Sets `content_security_policy` in extension
  manifest.


## Version 123

### Enhancements ###

* `* left` and `* right` can now be used to collapse or expand all
  tasks.


## Version 122

### Bug fixes ###

* More adjustments to task dragging between sections. See [#166][]

[#166]: https://github.com/mgsloan/todoist-shortcuts/issues/166


## Version 121

### Bug fixes ###

* Improves task dragging with sections. See [#166][]

[#166]: https://github.com/mgsloan/todoist-shortcuts/issues/166


## Version 120

### Bug fixes ###

* Fixes navigation to favorite items with newest Todoist verison
  (again!). See [#162][]


## Version 119

### Bug fixes ###

* Fixes the width of the help modal being too narrow.

### Enhancements ###

* Code switched over to using ES6, mostly by using the [lebab tool][].

[lebab tool]: https://github.com/lebab/lebab


## Version 118

* Fixes some console errors that resulted from incomplete fix to
  [#162][].


## Version 117

### Bug fixes ###

* Fixes navigation to favorite items with newest Todoist verison. See
  [#162][].

* Fixes scrolling with newest Todoist version. See [#163][].

[#162]: https://github.com/mgsloan/todoist-shortcuts/issues/162
[#163]: https://github.com/mgsloan/todoist-shortcuts/issues/163


## Version 116

### Bug fixes ###

* Fixed keyboard navigation for search box. See [#159][].

* Fix keyboard navigation to inbox and upcoming. See [#160][].

[#159]: https://github.com/mgsloan/todoist-shortcuts/issues/159
[#160]: https://github.com/mgsloan/todoist-shortcuts/issues/160


## Version 115

### Bug fixes ###

* Attempts to fix task selection on MacOS. See [#158][].

[#158]: https://github.com/mgsloan/todoist-shortcuts/issues/157


## Version 114

### Bug fixes ###

* A truly proper workaround for `ItemSelector` interface
  disappearing. It turns out control-click toggles task selection! I
  did not realize this until pointed out by a helpful Todoist
  developer. See [#156][].


## Version 113

### Bug fixes ###

* Proper workaround for `ItemSelector` interface disappearing. For
  every selection change, it now orchestrates a series of shift-clicks
  to construct the desired selection state. See [#156][].

* Fixes actions on multiple selections. See [#156][].

* Fixes navigation keys for labels / filters. See [#157][].

[#157]: https://github.com/mgsloan/todoist-shortcuts/issues/157


## Version 112

### Bug fixes ###

* Workaround `ItemSelector` interface disappearing. See [#156][]

  - `x` now behaves the same as shift-click (so, bizarrely), and
    displays a message explaining the behavior change.

  - Selecting by priority is disabled (hopefully temporarily).

  - These changes are non-ideal and will hopefully be fixed in the
    future.

[#156]: https://github.com/mgsloan/todoist-shortcuts/issues/154


## Version 111

### Bug fixes ###

* Fixes scrolling behavior when moving cursor up - adjusts for new
  header height.


## Version 110

### Bug fixes ###

* Fixes 'd' shortcut for task completion. See [#154]

[#154]: https://github.com/mgsloan/todoist-shortcuts/issues/154


## Version 109

### Bug fixes ###

* Disables debug logging accidentally enabled in version 108.


## Version 108

### Bug fixes ###

* Fixes task movement shortcuts in today / upcoming views.  See
  [#153][]

* Fixes `o` + `shift+o` (add task below / above) functionality in
  upcoming / label / filter views.

[#153]: https://github.com/mgsloan/todoist-shortcuts/issues/153


## Version 107

### Bug fixes ###

* Fixes scheduler shortcuts in task view mode. See [#152].

[#152]: https://github.com/mgsloan/todoist-shortcuts/issues/152


## Version 106

### Bug fixes ###

* Improves reliability of `shift+k` shortcut for moving task upwards.


## Version 105

### Bug fixes ###

* Fixes `s` for sorting by date. For now fix will only work in English
  version of Todoist. See [#142]

* Fixes `o` + `shift+o` (add task below / above) functionality within
  empty projects.

[#142]: https://github.com/mgsloan/todoist-shortcuts/issues/142


## Version 104

### Bug fixes ###

* Fixes `v` shortcut for moving a single task to project. See [#151][].

[#151]: https://github.com/mgsloan/todoist-shortcuts/issues/151


## Version 103

### Bug fixes ###

* Fixes `a` and `A` shortcuts for inserting first and last tasks. See
  [#150][].

[#150]: https://github.com/mgsloan/todoist-shortcuts/issues/150


## Version 102

### Bug fixes ###

* Prevents `* a` shortcut also triggering Todoist's native `a`
  shortcut for adding a task. May also fix other fall-throughs.


## Version 101

### Bug fixes ###

* Fixes `u` shortcut for clicking undo - broken by changes in expected
  page structure.


## Version 100

### Bug fixes ###

* Fixes functioning of `* o` shortcut for selecting all overdue tests.


## Version 99

### Bug fixes ###

* Most recent Todoist version changed the requirements for mouse
  events causing task buttons to get created.  This caused many
  operations on single tasks to no longer work.  It's now fixed by
  fiddlying with the mouse events a bit!  See [#149][].

[#149]: https://github.com/mgsloan/todoist-shortcuts/issues/149


## Version 98

### Bug fixes ###

* Fixes horizontal task movement sometimes skipping nesting levels

* Attempts to fix cursor disappearing after task movement.


## Version 97

### Bug fixes ###

* Fix assign shortcut. See [#148][]

[#148]: https://github.com/mgsloan/todoist-shortcuts/issues/148


## Version 96

### Enhancements ###

* The previous workaround removal for [#137][] made rescheduling /
  task movement clunky, because the task remained in inline edit mode
  after selecting a date / project. This is now fixed by not opening
  the inline editor, and instead using the original route for
  scheduling / move-to-project.

    - Sidenote: the reason this wasn't done before is that the buttons
      on the task are now lazily added on mouse hover, presumably to
      make initial render of large projects fater. I couldn't figure
      out which event to use to trigger this, till today I realized
      `mouseenter` does the trick.


## Version 95

### Enhancements ###

* Removes workaround introduced in version 85, which selected the task
  under the cursor to perform operations on it. This was related to
  the need for disambiguating attributes, tracked by [#137][].

  - This is particularly beneficial for the `t` / `T` scheduling
    shortcuts, as now the current scheduling information will appear.


## Version 94

### Bug fixes ###

* Version 93 inadvertently broke some functionality in agenda mode.
  Now fixed!


## Version 93

### Bug fixes ###

* Fix `c` shortcut for opening comments.  See [#146][].

* Fixes task movement in today and upcoming views.  See [#145][].

[#145]: https://github.com/mgsloan/todoist-shortcuts/issues/145
[#146]: https://github.com/mgsloan/todoist-shortcuts/issues/146


## Version 92

### Bug fixes ###

* Fixes a typo that probably broke a lot of things. (this release is
  coming minutes after version 91)


## Version 91

### Bug fixes ###

* Fixes task movement (mostly - there are still rough edges). See
  [#141][].

* Fixes `y` / `@` label picker shortcut. See [#143][]

* Fixes section finding code, which fixes `shift+g` navigation from
  label / filters to the agenda view of the task. See [#144][].

[#141]: https://github.com/mgsloan/todoist-shortcuts/issues/141
[#143]: https://github.com/mgsloan/todoist-shortcuts/issues/143
[#144]: https://github.com/mgsloan/todoist-shortcuts/issues/144


## Version 90

### Bug fixes ###

* Now works with non-english locales! Currently only on
  beta.todoist.com, but soon on todoist.com. This was made possible by
  changes made by helpful engineers at Doist! See [#137][].

* Cursor movement now skips over collapsed tasks. See [comment on
  #137][].

* Fixes a bug where `shift+enter` on a task with no link would open a
  new Todoist tab.

### Enhancements ###

* In navigate mode (`g`), backspace now deletes the last typed
  character, instead of exiting navigate mode.

[#137]: https://github.com/mgsloan/todoist-shortcuts/issues/137
[comment on #137]: https://github.com/mgsloan/todoist-shortcuts/issues/137#issuecomment-641874431


## Version 89

### Bug fixes ###

* Fixes `c` shortcut for opening comments. See [#140][]

* Fixes `u` shortcut for undo.

[#140]: https://github.com/mgsloan/todoist-shortcuts/issues/140


## Version 88

### Bug fixes ###

* Fixes editing of tasks. See [#138][].

* Fixes `o` + `shift+o` bindings for adding task before / after. See
  [#139][] / [#137][].

* Fixes `r` for opening reminders.

[#138]: https://github.com/mgsloan/todoist-shortcuts/issues/138
[#139]: https://github.com/mgsloan/todoist-shortcuts/issues/139


## Version 87

### Bug fixes ###

* Binds `e` shortcut to task deletion, since the concept of task
  archiving no longer exists in Todoist.  See [#132][].

* Bulk reschedule / move now popup a dialog explaining why they are
  disabled.

[#132]: https://github.com/mgsloan/todoist-shortcuts/issues/132


## Version 86

### Bug fixes ###

* Fixes restoring cursor position after an operation.


## Version 85

### Bug fixes ###

* Lots of fixes to work with Todoist version 1006. See [#135][] and
  [#136][]. The DOM changes that started in the Upcoming view haver
  rolled out everywhere else.  Unfortunately, now most functionality
  only works for the english version. This is hopefully temporary -
  see [#137][].

* One aspect of the workaround is that when there are no tasks
  selected, and the operation modifies the task under the cursor, it
  will become selected.  One happy consequence of this is that I
  believe most functionality now works in the 'Upcoming' view [#110][].

[#110]: https://github.com/mgsloan/todoist-shortcuts/issues/110
[#135]: https://github.com/mgsloan/todoist-shortcuts/issues/135
[#136]: https://github.com/mgsloan/todoist-shortcuts/issues/136
[#137]: https://github.com/mgsloan/todoist-shortcuts/issues/137


## Version 84

### Bug fixes ###

* Fixes `g` navigation to `Upcoming` section.  Reuses the character
  `n`, for the benefit of those with muscle memory for the old `Next 7
  days`.

* Fixes `h` key (cursor left) - it was being interpreted as a new
  native Todoist shortcut to switch to upcoming view. See [#134][].

[#134]: https://github.com/mgsloan/todoist-shortcuts/issues/134


## Version 83

### Bug fixes ###

* Fixes operations on multiple tasks after more changes in Todoist.
  Unfortunately, those changes in Todoist mean there are no longer
  informative attributes to disambiguate the buttons. So, the
  workaround relies on English text, and so these operations are still
  broken for non-english locales. See [#129][].

* Now pops up a notification that Todoist no longer supports archive
  on multiple tasks. See [#132][].

[#129]: https://github.com/mgsloan/todoist-shortcuts/issues/129
[#132]: https://github.com/mgsloan/todoist-shortcuts/issues/132


## Version 82

### Bug fixes ###

* Fixes multi task operations. The toolbar no longer has an id
  attribute, so matching on a class instead.


## Version 81

### Bug fixes ###

* Fixes task selection, broken in Todoist version 1000.  See [#127][].

[#127]: https://github.com/mgsloan/todoist-shortcuts/issues/127


## Version 80

### Enhancements ###

* Adds support for marking a task complete in the task view via `d`.


## Version 79

### Enhancements ###

* Add support for clicking clockify extension buttons via `ctrl+c`
  (also works for toggl button, as before). See [#121][].

[#121]: https://github.com/mgsloan/todoist-shortcuts/issues/121


## Version 78

### Bug fixes ###

* Works around a weird issue where there are missing drag-and-drop
  targets when dragging tasks upwards. The workaround is to overshoot
  the drag and then bring it back to where it should go. See [#120][].

* When tasks are dragged beyond the viewport, they now get scrolled
  into view.

[#120]: https://github.com/mgsloan/todoist-shortcuts/issues/120


## Version 77

### Bug fixes###

* Fixes keyboard interaction with task view. See [#114][].

* Fixes shift+enter to open links on Firefox. See [#117][].

[#114]: https://github.com/mgsloan/todoist-shortcuts/issues/114
[#117]: https://github.com/mgsloan/todoist-shortcuts/issues/117


## Version 76

### Enhancements ###

* Added `p` alias (mnemonic "postpone") in scheduler shortcuts for
  postpone / smart schedule. See [#113][].

[#113]: https://github.com/mgsloan/todoist-shortcuts/issues/113


## Version 75

### Bug fixes ###

* Better fix to the recent changes in Todoist's registration of
  keyboard events. See [#111][] and [#112][].

[#112]: https://github.com/mgsloan/todoist-shortcuts/issues/112


## Version 74

### Bug fixes ###

* Fixes an issue on beta.todoist.com where a mix of todoist-shortcuts
  and Todoist's keyboard handling was being used. See [#111][].

* Further improvement to handling of Todoist's deferred
  initialization.

[#111]: https://github.com/mgsloan/todoist-shortcuts/issues/111


## Version 73

### Bug fixes ###

* Fixes an issue where the extension failed to initialize properly if
  Todoist didn't already initialize some parts of the UI.


## Version 72

### Bug fixes ###

* Fixes navigation pane position on non-beta todoist. See [#109][].

[#109]: https://github.com/mgsloan/todoist-shortcuts/issues/109


## Version 71

### Bug fixes ###

* Fixes task editing and task view keybindings on
  beta.todoist.com. See [#105][].

* Fixes setting priority on multiple tasks at once. See [#106][].

* Fixes `shift+enter` shortcut to open links. See [#107][].

* Fixes a bug where "discard task" dialog would not display reliably
  when pressing escape on quick add dialog.

* Now ignores scrolling shortly after keyboard shortcuts open task
  menu (occurs when item is near bottom of window).

[#105]: https://github.com/mgsloan/todoist-shortcuts/issues/105
[#106]: https://github.com/mgsloan/todoist-shortcuts/issues/106
[#107]: https://github.com/mgsloan/todoist-shortcuts/issues/107


## Version 70

### Bug fixes ###

* Fixes a bug where the keymap would get stuck on task view even
  though the task view was not open.

* Makes it so that the keymap does not switch away from navigate mode
  until it is finished.


## Version 69

### Enhancements ###

* Adds `shift+c` shortcut for clicking toggl button in task view.

### Bug fixes ###

* Fixes `t s` shortcut for clicking suggested date in scheduler.


## Version 68

### Bug fixes ###

* Fixes keyboard interaction with "Are you sure you want to discard
  your current task?" modal when cancelling quick-add.


## Version 67

### Enhancements ###

* New keyboard shortcut, `+`, which opens assign dialog. See [#89][].

* New keyboard shortcut, `* o`, which selects overdue tasks. See [#91][].

[#89]: https://github.com/mgsloan/todoist-shortcuts/issues/89
[#91]: https://github.com/mgsloan/todoist-shortcuts/issues/91

### Bug fixes ###

* Fixes "i" for opening task view when the toggl-button extension is
  also being used. See [#96].

[#96]: https://github.com/mgsloan/todoist-shortcuts/issues/96


## Version 66

### Bug fixes ###

* Fixes task selection, a bug introduced when improving no-cursor handling.
  See [#95][].

[#95]: https://github.com/mgsloan/todoist-shortcuts/issues/95


## Version 65

### Enhancements ###

* Adds shortcuts for the new task view side pane. See [#88][]. Many familiar
  shortcuts work in that view. The new ones are:

  - `i` to open the task view.

  - `s` to view subtasks section.

  - `c` to view comments section.

  - `shift+h` to view activity section.

  - `h` to navigate to parent task.

* Adds `shift+r` shortcut to open reminders dialog.

* Improves error handling for the case where there is no cursor.

[#88]: https://github.com/mgsloan/todoist-shortcuts/issues/88


## Version 64

### Bug fixes ###

* Fixed smart scheduler on multiple items, from changes in Todoist
  elements. See [#90]

* Adds an empty keymap for when new task view pane is visible.  This
  way keypresses don't manipulated tasks that are obscured.

* Fixes schedule keybinding on beta.todoist.com. See [#92]

[#90]: https://github.com/mgsloan/todoist-shortcuts/issues/90
[#92]: https://github.com/mgsloan/todoist-shortcuts/issues/92


## Version 63

### Bug fixes ###

* Fixed opening of task menu with Todoist version 972. This caused
  various shortcuts to not work on individual tasks. See [#87]

* Fixed getting the name of the section a task is in. This fixes some
  logic that prevents task motion in the overdue list, and causes the
  cursor to not follow a task if it changes section.

[#87]: https://github.com/mgsloan/todoist-shortcuts/issues/87


## Version 62

### Enhancements ###

* Previously, quickly typing editor actions would result in keystrokes
  in the textual time input.  This is now fixed!

### Bug fixes ###

* Now ignores most keystrokes when Todoist modal dialogs are
  displayed.  For the task deletion and discarding modals, `Enter`
  will now accept the action, while `Escape` will cancel it. See [#82]

[#82]: https://github.com/mgsloan/todoist-shortcuts/issues/82


## Version 61

### Enhancements ###

* Just `z` alone now undos, matching GMail keyboard shortcuts.

### Bug fixes ###

* Fixes scheduling shortcuts which broke due to changes in Todoist
  Version 968. See [#85]

* Fixes bulk archive, bulk delete, and labeling shortcuts which broke
  due to changes in Todoist Version 968. See [#84]

[#85]: https://github.com/mgsloan/todoist-shortcuts/issues/85
[#84]: https://github.com/mgsloan/todoist-shortcuts/issues/85


## Version 60

### Enhancements ###

* Loading of help modal iframe now deferred to first use

### Bug fixes ###

* Adds documentation of `?` for bringing up the keyboard shortcuts
  guide.  See [comments on #81]

[comments on #81]: https://github.com/mgsloan/todoist-shortcuts/issues/71#issuecomment-521128504


## Version 59

### Bug fixes ###

* Fix some bugs with things misbehaving after navigating to a
  different project.  See [#81]

[#81]: https://github.com/mgsloan/todoist-shortcuts/issues/81


## Version 58

### Bug fixes ###

* Fixes toggling visibility of parent projects when navigating to a
  hidden project.


## Version 57

### Bug fixes ###

* Fixes toggling of navigation sections.  See [#80]

[#80]: https://github.com/mgsloan/todoist-shortcuts/issues/80


## Version 56

### Bug fixes ###

* Fixes navigation bug when there are navigation items with the same
  name corresponding to a default key sequence.  See [#79]

[#79]: https://github.com/mgsloan/todoist-shortcuts/issues/79


## Version 55

### Bug fixes ###

* Makes the extension work on `chrome.todoist.com/app`.  See [#78]

[#78]: https://github.com/mgsloan/todoist-shortcuts/issues/78


## Version 54

### Bug fixes ###

* Fixes `s` binding for sort by date - see [#76].

[#76]: https://github.com/mgsloan/todoist-shortcuts/issues/76


## Version 53

### Bug fixes ###

* Fixes functioning of extension with Todoist version 956.  Thanks to
  quick fixes from [Jed Verity][glortho] and [Adam
  L. Rich][adamleerich].  See [#72], [#73], and [#75].

[glortho]: https://github.com/glortho
[adamleerich]: https://github.com/adamleerich
[#72]: https://github.com/mgsloan/todoist-shortcuts/issues/72
[#73]: https://github.com/mgsloan/todoist-shortcuts/pull/73
[#75]: https://github.com/mgsloan/todoist-shortcuts/pull/75


## Version 52 ##

### Enhancements ###

* Add a proper modal which nicely displays keyboard shortcuts.  Thanks
  to kimaero on GitHub, who created the Google Sheet which gets
  presented. See [#71].

[#71]: https://github.com/mgsloan/todoist-shortcuts/issues/71


## Version 51 ##

* I fumble fingered "Cancel and disable version" on the mozilla
  upload, which caused version 50 to not exist in the listing of
  mozilla extensions.  So creating version 51 to work around that...


## Version 50 ##

### Bug fixes ###

* Changes to Todoist made it so that when Todoist is in 'mini' mode
  for narrow browsers, pressing 'g' to enter navigation mode no longer
  caused the sidebar to be displayed.  This is now fixed by making
  todoist-shortcut's CSS match Todoist's. See [#70].

[#70]: https://github.com/mgsloan/todoist-shortcuts/issues/67


## Version 49 ##

### Bug fixes ###

* Makes moving tasks work with recent Todoist versions. ([#68])

* Workaround (hopefully temporary) for [#67], where Todoist's undo
  keybinding doesn't work.

* Makes moving tasks around scroll properly.

* If moving a task fails, no longer leaves it in dragging state.

* Improves performance of cursor motion, where there was a regression
  recently.

[#67]: https://github.com/mgsloan/todoist-shortcuts/issues/67
[#68]: https://github.com/mgsloan/todoist-shortcuts/issues/68


## Version 48 ##

### Bug fixes ###

* Fixes some bugs with moving tasks up / down.  In particular, there
  was a poor interaction with the new mouse hover code that caused
  cursor focus to get stuck.


## Version 47 ##

### Enhancements ###

* Improvement to visual consistency by having the cursor's color match
  the priority 3 blue.


## Version 46 ##

### Enhancements ###

* Switches to only using the blue bar cursor, rather than using the
  drag handle.  This is more uniform, reduces code complexity,
  resolves a tricky problem ([#65]), and allows manipulation of nested
  tasks when viewing Today / Next 7 Days ([#26]).

[#65]: https://github.com/mgsloan/todoist-shortcuts/issues/65
[#26]: https://github.com/mgsloan/todoist-shortcuts/issues/26

### Bug fixes ###

* Fixes a bug where cursor movement wouldn't select nested tasks in
  filter or search list. See [#64].

[#64]: https://github.com/mgsloan/todoist-shortcuts/issues/64


## Version 45 ##

### Enhancements ###

* Improved performance when used with [toggl-button] extension.

* Removes the hack making icons visible when task is cursored. Turned
  out to be more trouble than it was worth, caused some tricky
  problems.


## Version 44 ##

### Enhancements ###

* Adds `shift+c` shortcut for clicking [toggl-button].

* Icons that are only visible when a task is hovered, like the
  comments and [toggl-button], will now move with the cursor.

[toggl-button]: https://toggl.com/toggl-button/


## Version 43 ##

### Bug fixes ###

* Fixes display of deprecation notice for `d` when displayed in narrow
  windows (in particular, the iframe used by [Todoist for Gmail]).


## Version 42 ##

### Enhancements ###

* Changes the scheduler keybinding for "today" to `c` (instead of
  `d`). This is to make it less likely that tasks accidentally get
  marked done. See [#52]

* Keyboard shortcuts now work in todoist iframes.  In particular,
  todoist-shortcuts can now be used along with the [Todoist for
  Gmail].

[#52]: https://github.com/mgsloan/todoist-shortcuts/issues/52
[Todoist for Gmail]: https://chrome.google.com/webstore/detail/todoist-for-gmail/clgenfnodoocmhnlnpknojdbjjnmecff?hl=en


## Version 41 ##

### Bug fixes ###

* Fixed a bug where cursor movement would select collapsed tasks.


## Version 40 ##

### Enhancements ###

* When scheduling a recurring task, `s` now postpones the task.


## Version 39 ##

### Bug fixes ###

* Workaround for an issue where moving / indenting / dedenting a task
  causes the window to scroll up a bit. See [#58].

* Removes note about task indenting not working, as it seems to no
  longer be a problem. See [#50]

[#58]: https://github.com/mgsloan/todoist-shortcuts/issues/58
[#50]: https://github.com/mgsloan/todoist-shortcuts/issues/50


## Version 38 ##

### Bug fixes ###

* On initial login, there was some lag for the theme to be
  applied. This caused the background color for navigation tips to be
  wrong. This version fixes this problem.

* Makes it so that scheduling via text entry (`T`) can work with
  multiple tasks selected. See [#24].

[#24]: https://github.com/mgsloan/todoist-shortcuts/issues/24


## Version 37 ##

### Bug fixes ###

* Fixes scheduling of unscheduled tasks. See [#56]

[#56]: https://github.com/mgsloan/todoist-shortcuts/issues/56


## Version 36 ##

### Enhancements ###

* When scheduling multiple items, `s` now opens the smart
  scheduler. Within the smart scheduler, `enter` applies the updates,
  and `escape` cancels. See [#53]

[#53]: https://github.com/mgsloan/todoist-shortcuts/issues/53

### Bug fixes ###

* Fix a crucial bug where most actions weren't working. Adapts to
  changes that affect finding Todoist menus.

* Fixes / improves rescheduling of a single task.

* Fixes updating of internal `viewMode` variable on initial load,
  likely due to slight changes in Todoist behavior. Without this fix,
  some functions might not work until after navigation.


## Version 35 ##

### Enhancements ###

* When navigating to a project / label / filter that is not visible
  due to collapsed parents, the project will now be made visible.


## Version 34 ##

### Enhancements ###

* Improves support for new scheduler added in Todoist
  version 925. This scheduler was previously available on
  beta.todoist.com, and so both schedulers were supported. Since the
  old scheduler no longer exists, support for it has been removed.

* Bump to Todoist version 925


## Version 33 ##

### Enhancements ###

* Documents that task indentation is currently broken, and that task
  motion in general is fiddly. See [#50].

* When navigating to a project that has sub-projects that are
  collapsed, always expands the listing and continues with navigation
  mode. As a side effect, this nicely adapts to a behavior change
  included in Todoist version 908, which allows toggling between
  seeing all sub-projects or just the one parent project. When using
  keyboard bindings, you will now only encounter the first mode,
  rather than arbitrarily toggling between the modes.

* Bump to Todoist version 924

[#50]: https://github.com/mgsloan/todoist-shortcuts/issues/50

### Bug fixes ###

* Fixes an issue with moving the cursor between multiple projects,
  when viewing a parent project. It wouldn't change which project is
  considered to be focused, and so actions like sorting by priority
  would apply to the wrong project.

* When inserting new tasks or editing tasks, the cursor position after
  editing would often be surprising. I believe this is due to Todoist
  behavior changes. However, happily the new behavior allows this
  mechanism to be much more reliable.


## Version 32 ##

### Enhancements ###

* Adds a binding, `G`, to navigate to task's project, or select in
  agenda if already on project.

* Bump to Todoist version 920


## Version 31 ##

### Bug fixes ###

* Fixes a really bad bug with the extension on FireFox, where original
  Todoist keybindings wouldn't work, and even many browser keybindings
  wouldn't work. See [#46]

* Fixes use of `ctrl+z` on FireFox.

[#46]: https://github.com/mgsloan/todoist-shortcuts/issues/46


## Version 30 ##

### Enhancements ###

* Keybindings for interacting with text entry of new scheduler on
  https://beta.todoist.com :

    - `backspace` or `delete` clears and focuses the text date entry.

    - `enter`focuses the text date entry without clearing it.

* Also in the new scheduler mode, `s` is now a shortcut for using the
  "suggested" date.

* Bump to Todoist version 919

### Bug fixes ###

* Fixes `enter` binding to edit task text, which seems to have broken
  with updates in Todoist 919. Easy fix, though!


## Version 29 ##

### Bug fixes ###

* Fix behavior of multi selection with new scheduler on
  https://beta.todoist.com .  See [#49].


## Version 28 ##

### Enhancements ###

* Updated to work with new scheduler visible on
  https://beta.todoist.com .  See [#49].

[#49]: https://github.com/mgsloan/todoist-shortcuts/issues/49


## Version 27 ##

### Enhancements ###

* `0` is now an alias for level 4 priority, the default priority. So,
  `0` and `4` do the same thing, as well as `* 0` and `* 4` for
  selecting tasks with default priority.

* In navigation mode, up / down arrows now scroll up / down a bit.

* Fixes navigation to favorite items, broken due to upstream changes
  of DOM structure.

* Fixes styling of navigation links, since they were being clipped,
  due to upstream CSS changes. I like this new approach better anyway,
  tightens up the tips.

* Bump to Todoist version 918.


## Version 26 ##

### Bug fixes ###

* Collapses nested tasks before moving up / down, makes task
  movement better behaved. See [#29]

[#29]: https://github.com/mgsloan/todoist-shortcuts/issues/29


## Version 25 ##

### Enhancements ###

* Adds '&' keybinding for task duplication.


## Version 24 ##

### Bug fixes ###

* Actual working fix to the bug where no cursor would be displayed
  for a custom filter like "today & p1".

* Fixes `h` and `l`, due to changes in class names used by
  Todoist.  See [this comment on #46][#46c2]

[#46c2]: https://github.com/mgsloan/todoist-shortcuts/issues/46#issuecomment-425962924


## Version 23 ##

### Bug fixes ###

* Attempted fix of a bug where no cursor would be displayed for a
  custom filter like "today & p1".


## Version 22 ##

### Bug fixes ###

* Fixes a bug where project navigation didn't work for some
  projects with emojis. See [#44]

* Fixes a bug where project navigation didn't work for favorite
  labels.  I suspect that this is due to a change in CSS class name
  between version 911 and 914.

[#44]: https://github.com/mgsloan/todoist-shortcuts/issues/44


## Version 21 ##

### Bug fixes ###

* Fixes original todoist keybindings `a` / `A` for adding tasks to the
  top / bottom of the list. See [#41]

* Fixes bug that prevented Todoist's ability to display a particular
  task within a listing. See [#42]

[#41]: https://github.com/mgsloan/todoist-shortcuts/issues/41
[#42]: https://github.com/mgsloan/todoist-shortcuts/issues/42


## Version 20 ##

### Bug fixes ###

* The most recent bugfix release broke some keybindings.  This
  release has a bugfix that works around [mousetrap#430].

[mousetrap#430]: https://github.com/ccampbell/mousetrap/issues/430


## Version 19 ##

### Bug fixes ###

* Fixes a bug where it didn't function at all on Firefox, for
  puzzling reasons related to the keypress event handler. See [#40].

* Moving tasks up and down via `shift-j` / `shift-k` now works in agenda
  mode (today / next 7 days). I believe this was enabled by a change in
  Todoist behavior.

* Fix a bug where moving a task left would sometimes move the task into
  a project. See [#39].

[#39]: https://github.com/mgsloan/todoist-shortcuts/issues/39
[#40]: https://github.com/mgsloan/todoist-shortcuts/issues/40


## Version 18 ##

### Enhancements ###

* Adds support for manual sync via `ctrl+s`. See [reddit thread].

* Adds use of backtick and shift+backtick to cycle through top
  level filters (inbox / today / next 7 days + favorites). This is
  the same keybinding that GMail uses for a similar purpose.

* Adds support for sorting by name via `n`. See [#36]

[reddit thread]: https://www.reddit.com/r/todoist/comments/92j1qz/todoistshortcuts_browser_extension_adding/e3a2kbt/
[#36]: https://github.com/mgsloan/todoist-shortcuts/issues/36


## Version 17 ##

### Enhancements ###

* Adds support for clicking the first link in a task via
  shift+enter. See [#33].

* Bump to Todoist version 911.

### Bug fixes ###

* Fixes scheduling actions and navigation to inbox / today / next
  7 days, which no longer worked due to dom updates in Todoist
  version 911.

[#33]: https://github.com/mgsloan/todoist-shortcuts/issues/33


## Version 16 ##

### Enhancements ###

* Adds support for cursor navigation while in bulk move and bulk
  reschedule mode. Also allows switching between these two bulk
  modes.

* Adds an internal function for clicking the "import from tempalte" menu
  item.  To avoid binding everything to keys, there is no default
  keybinding for this.  However, if you modify the code for the
  extension then you can use it.  See [#30].

* Bump to Todoist version 910.

### Bug fixes ###

* No longer attempts to reselect tasks after priority change as this
  triggers a bug. See [#32].

* Fixes a display bug for the navigate mode tips for toggling project /
  label / filter sections. See [#34].

* Fixes a bug where escape would not exit bulk move mode.

[#30]: https://github.com/mgsloan/todoist-shortcuts/issues/30
[#32]: https://github.com/mgsloan/todoist-shortcuts/issues/32
[#34]: https://github.com/mgsloan/todoist-shortcuts/issues/34


## Version 15 ##

* Keyboard events not handled by todoist-shortcuts now get passed
  along to Todoist. See
  [#25](https://github.com/mgsloan/todoist-shortcuts/issues/25).

* Now supports navigation to favorite filters / labels. See
  [#31](https://github.com/mgsloan/todoist-shortcuts/issues/31).


## Version 14 ##

* Bump to Todoist version 908. This version of the extension fixes
  issues with todoist-shortcuts due to some recent changes of
  todoist's DOM structure.

* Improved reliability of task motion commands.

* Adds 'c' keybinding for opening comment dialog.


## Version 13 ##

* Enter can now be used to confirm deletion.

* Pressing escape will now exit out of inline task adding.

* Change "remove label" keybinding to use `@` instead of `l`.  The old
  keybinding shadowed the expand + navigate in keybinding.

* Cursor is now visible in filters and labels! See
  [#14](https://github.com/mgsloan/todoist-shortcuts/issues/14).

* Bump to Todoist version 907.


## Version 12 ##

* Removed some warnings which can occur during normal operation
  (particularly when no tasks are visible). Warnings that can happen
  during normal operation should only happen when the action can not be
  performed for some reason, and should be reasonably human readable.


## Version 11 ##

* Fixed icons


## Version 10 ##

* Due to Todoist making some changes to their code, it is now possible
  to use todoist-shortcuts with languages other than english.
  See [#2](https://github.com/mgsloan/todoist-shortcuts/issues/2)

* In navigate mode, `t` is no longer used to navigate to "Today",
  instead `g` is used. The main reason for this is that in navigate
  mode, it is now possible to use `tp` / `tl` / `tf` to toggle the
  different sections. These would not have b These would not have been
  typeable if `t` was taken. This also makes it a little faster to
  navigate to the commonly used "Today" section.

* Now supports navigating to labels and filters. See
  [#3](https://github.com/mgsloan/todoist-shortcuts/issues/3)

* In navigation mode, selecting a project with collapsed sub-projects will
  cause them to expand. To collapse, just re-select the same project.

* Adds `* l` and `* h` to expand or collapse all task nesting. See
  [#18](https://github.com/mgsloan/todoist-shortcuts/issues/18)

* `?` shortcut for keyboard shortcuts help now links to the readme for
  that particular release, rather than master.

* Typing "x" in an input field no longer toggles selection. See
  [#15](https://github.com/mgsloan/todoist-shortcuts/issues/15)

* There was a bug where after editing a task, the task before it would end
  up selected. This is now fixed. See
  [#9](https://github.com/mgsloan/todoist-shortcuts/issues/9)

* Some Todoist internals are now directly invoked, to handle
  selection more efficiently. See
  [#11](https://github.com/mgsloan/todoist-shortcuts/issues/11)

* Previously key sequences like `* a` required that you not delay more
  than 1 second between keystrokes, due to behavior in the
  [mousetrap](https://github.com/ccampbell/mousetrap) library. This
  is no longer the case.

* Fixes an issue where typing `g` followed by some key that does nothing
  would cause the cursor to move down one.

* Scrolling behavior and cursor mouse behavior is now less glitchy.

* `ctrl+z` is now a synonym for undo.

* Adds `* t` keybinding to enter bulk reschedule mode.

* Adds `* v` keybinding to enter bulk move mode.

* Using `h` to collapse will now collapse the parent if the cursor
  is already collapsed

* Using `l` to expand will now move the cursor to the first
  sub-project.

* `x` can no longer be held down to do multiple selections.  This is due
  to key sequences like `jxjxjxjx` being glitchy.  There is a constant
  called `MULTISELECT` in the source that can be set to `true` to bring
  back the multiselection behavior.

* Bump to todoist version 904.


## Version 9 ##

* Bump to todoist version 893.  Fixes for things that changed.

* Only has noisy version mismatch if your todoist version is too old.

* Now also works on https://beta.todoist.com/app

* Adding tasks via `o` and `O` now works when cursor is on an overdue task
  in agenda view

* Fixes to issues with cursor position after task add. See
  https://github.com/mgsloan/todoist-shortcuts/issues/8

* Old scheduling binding for "n" removed, use "d" instead.


## Version 8 ##

* Now uses the standard drag-and-drop handle to indicate the cursor.

* 'x' can be held down to select / deselect every task the cursor is moved to.

* Vertical auto-scrolling now takes into account top bar occlusion.


## Version 7 ##

* Bump to todoist version 892.

* No longer has a noisy warning by default for version mismatch.

* "r" for sort by assignee now works.

* Scheduling keybinding for "today" is now "d" instead of "n".

* Now "move to project" is back to being "v" instead of "m".


## Version 6 ##

* Bump to todoist version 891.

* Defaults to allow applying done / archive directly to cursor. Issue #1

* Implements sorting keybindings. Issue #1

* Adds "^" and "$" keybindings for moving cursor to first and last task.

* Cursor is now stable even when task gets re-scheduled or moved.

* When navigate mode is activated ("g"), the left pane will now become
  visible even when the browser window is narrow and so in 'mini mode'.


## Version 5 ##

* Bump to todoist version 890.

* Have mismatch warning tell you which version was expected.


## Version 4 ##

* Last version was hastily released, this fixes "move to project" (release
  made minutes after the last one)


## Version 3 ##

* Now "move to project" is "m" instead of "v".


## Version 2 ##

* Most default todoist keybindings like 'u' for undo now work too.

* Fixes position of version mismatch warning when viewing more
than a screenful.

* No longer warns about potential mismatch with todoist version 889
