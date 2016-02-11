---
id: editor-basics
title: Basics
layout: docs
permalink: /docs/editor/basics/
---

Nuclide is a code editor built on the backbone of [GitHub's Atom text editor](https://atom.io).
Like other code editors and IDEs, there is a familiar look and feel to Nuclide. On the left-hand
side is your project tree, which includes associated files and folders. On the right-hand side is
the main editor that contains the code and text for files in your project. And on the bottom is a
status bar providing quick-look information such as errors, the path of the current file relative
to your project root, the type of file that is open, and other context-aware data.

![](/static/images/docs/editor-basics-intro.png)

## Opening

Assuming you have it [installed](/docs/editor/setup/), Nuclide is opened by opening Atom via mouse
(Dock, Applications folder, etc.) or at the command-line in a terminal window by running:

```bash
$ atom
```

By default, when you open Nuclide, the Home page appears.

![](/static/images/docs/editor-basics-homepage.png)

The Nuclide Home page gives you quick access to common Nuclide tools and features, as well as
information regarding how to provide feedback.

## Project and File Explorer

The project and file explorer is on the left-hand side of Nuclide. This is where you can open
projects, navigate through your project to open files in the [editing area](#editing-area),
create new files and folders, etc.

### Adding Projects

The first time you open Nuclide, there will be no projects or files open. Instead you will see two
options in the explorer. The first is to open a local project. The second is to open a project on a
[remote machine](/docs/remote/).

![](/static/images/docs/editor-basics-adding-projects.png)

When you choose a project to open, you are choosing the root directory of that project. Upon
opening, the file explorer turns into a file tree, with the top of tree as the root.

![](/static/images/docs/editor-basics-file-tree.png)

To remove a project from the explorer, `right-click` on the root, and choose
`Remove Project Folder`.

### Multiple Projects

You can have more than one project open at a time. To open a second project, `right-click` anywhere
in the explorer window and choose `Add Project Folder` or `Add Remote Project Folder`.

> You can have both local and remote projects open at the same time.

With multiple projects open, default searching for files and in files will span both projects.
However, features such as debugging and error checking will still occur per project.

> For the `Find | Find In Project` task, you can add project-level granularity by specifying the
> root of the desired project as a filter for the search.

### Changed Files

If your project is under source control, the explorer will highlight the files that have changed in
your project since your last commit.

![](/static/images/docs/editor-basics-explorer-changed-files.png)

### Context-Aware Menu

The explorer has a context-aware menu that is shown when you `right-click`. This menu provides
options such as adding new projects, searching within the project, opening the current file in
Diff View (assuming you are working in a Mercurial repository), etc.

![](/static/images/docs/editor-basics-explorer-context-aware.png)

## Editing Area

The editing area is the main area to edit your code and text files. Each file is represented by a
tab. You can split this area into various panes for easier modification of multiple files.
The editing area is also where you will find specialized tabs for the Nuclide Home page,
the settings page, etc.

### File Navigation

Navigating between files and within files is the same as in
[Atom](https://atom.io/docs/v1.5.0/using-atom-moving-in-atom).

You can quickly switch between open files by using `ctrl-tab` to cycle right and `ctrl-shift-tab` to
cycle left.

Within files you can go straight to a line number by pressing `ctrl-g`. And if your project uses
a supported language, you can also jump to symbols with `cmd-r` (`ctrl-r` on Linux).

![](/static/images/docs/editor-basics-editing-area-symbols.png)

### Panes

Pane manipulation in Nuclide is different depending on whether you use menus or the keyboard.

If you use the menu to manipulate panes, Nuclide is also similar to
[Atom](https://atom.io/docs/v1.5.0/using-atom-panes) when it comes to splitting the editing area
into multiple panes. (e.g., `File | Panes | ...`). When adding a pane, the currently active file is
*copied* into the new pane. This is useful for editing different sections of the same file at
the same time.

> If you open the same file in multiple panes, any edits made in the file in one pane will be
> immediately reflected in that file in the other panes.

However, if you use the keyboard shortcuts to manipulate panes (e.g., `cmd-k <arrow>`), then there
is slightly different behavior. If you are adding a pane, then the currently active file is *moved*
to the new pane.

![](/static/images/docs/editor-basics-editing-panes.png)

### Search

Most of the searching actions are the same as
[Atom](https://atom.io/docs/v1.5.0/using-atom-find-and-replace). For example, you can search within
a file (e.g., `cmd-F`) or throughout your entire project(s) (e.g., `cmd-shift-F`).

In addition to the basic Atom searching, Nuclide adds an additional powerful search functionality
that allows you to search in various contexts. Omnisearch (`cmd-T` on Mac and `ctrl-T` on Linux)
provides a way to search, all at once, across your project, within your files, code symbols, etc.

![](/static/images/docs/editor-basics-editing-omnisearch.png)

### Context-Aware Menu

The explorer has a context-aware menu that is shown when you `right-click`. This menu provides
options such as adding and closing panes, setting and removing breakpoints, showing line-by-line
blame (assuming that information is available), etc.

![](/static/images/docs/editor-basics-editing-context-aware.png)

## Status Bar

The status bar in Nuclide builds upon the
[Atom status bar package](https://github.com/atom/status-bar). Nuclide adds powerful new
features to the status bar, including code diagnostics and remote connection status.

![](/static/images/docs/editor-basics-status-bar-intro.png)

### Code Diagnostics

If you are using a supported language that provides a linting and/or typechecking capability
(e.g., Hack or Flow), then code diagnostics is built directly into Nuclide for that language.

![](/static/images/docs/editor-basics-status-bar-diagnostics.png)

### Remote Connection Status

If you are connected to a project on a remote machine, clicking on the remote connection icon on
the status bar will provide information about the current status of that connection. Generally, if
all is well, the connection should say "Healthy".

![](/static/images/docs/editor-basics-status-bar-connection.png)

> If you check the connection against a local project, you will get information regarding whether
> the current active file exists on the local filesystem.

### File Encoding

The default file encoding for Atom is `UTF-8`. Clicking on this in the status bar allows you to
change the encoding of the current file.

### Language Selection

Atom determines the language of the current file. Normally this is correct. However, you can change
the language, and Atom will then change its syntax highlighting appropriately.

### Branch

Assuming your project is under source control, the status bar also shows the current branch on
which you are working.

## Command Palette

Atom is highly flexible in how you perform actions. Nuclide adds actions as well. There is a
variety of menu options. And many menu commands are equally accessible from the keyboard as well.

The Command Palette shows you every available command available in Atom and Nuclide.

`cmd-shift-P` toggles the Command Palette.

![](/static/images/docs/editor-basics-command-palette-intro.png)

By typing in the textbox of the palette, you can narrow down the options that match your search.

![](/static/images/docs/editor-basics-command-palette-search.png)
