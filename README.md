# To-Do List App

Manage daily tasks with add, edit, delete and completion controls, a RecyclerView list, status filters and durable local SQLite storage.

Pynexia Android Development / Week 2.

[Hosted showcase](https://engeyad.github.io/pynexia-week2-todo/) · [PDF report](https://engeyad.github.io/pynexia-week2-todo/downloads/To-Do-List-App-Report.pdf) · [APK](https://engeyad.github.io/pynexia-week2-todo/downloads/To-Do-List-App.apk) · [Submission ZIP](https://engeyad.github.io/pynexia-week2-todo/downloads/To-Do-List-App.zip)

## Implementation

### Task CRUD

Each task has a required title, optional details and a stable ID. SQLite stores all fields. A custom ListAdapter binds each item and its actions.

### Completion and filtering

A checkbox persists the done flag and adds a strike-through title. All/Open/Done filters and literal text search can be combined. The count reports completed versus total tasks.

### Lifecycle and feedback

Invalid titles show field errors. Delete requires confirmation. Background database work avoids blocking the UI; ViewModel retains in-flight editor saves.

## Run

Open the repository root in Android Studio. Install SDK 35 and Build Tools 35.0.0, use JDK 17 or 21 and sync Gradle. Run `todo` on Android 8.0/API 26 or newer. AGP 8.9.1; Gradle wrapper 8.11.1. Initial sync needs internet.

```powershell
.\gradlew.bat :todo:assembleDebug :todo:testDebugUnitTest :todo:lintDebug
.\gradlew.bat :todo:connectedDebugAndroidTest
```

The second command requires an emulator/device. On macOS/Linux use `chmod +x gradlew` and `./gradlew`.

## Walkthrough

1. Tap New task, enter a title and optional details, then Save.
2. Mark the checkbox and confirm the title is crossed out.
3. Switch between Open and Done, then reopen the app to check persistence.
4. Edit, search, uncheck or delete a task. Cancelling deletion preserves it.

## Verification

4 JVM tests and 4 device tests passed with no failures, errors or skips. Lint: 0 errors and 18 warnings without suppression. Tested 2 November 2026 on Pixel 8 emulator, Android 17/API 37 (37.1 image), x86_64. No physical-device or API 26 run. See `verification/` for results with local paths redacted.

Validation and search, SQLite CRUD/reopen, UI add/edit/delete/cancel, editor recreation, completion persistence and All/Open/Done filtering.

## Scope

No reminders, due dates, notifications or cloud sync; these are outside the assignment. Clearing app data/uninstalling removes tasks. SQLite storage is not encrypted.

APKs are debug signed for evaluation. Hosted pages show actual screenshots and downloads, not Android emulation. No Pynexia form is submitted automatically.

## شرح عربي

ينظم التطبيق المهام اليومية مع الإضافة والتعديل والحذف وتحديد المهمة كمكتملة. يحتفظ بحالة الإنجاز محليًا، ويتيح عرض جميع المهام أو المفتوحة أو المكتملة والبحث في محتواها. ترتبط الأزرار ومربعات الاختيار بالسجل الصحيح حتى عند تغيّر ترتيب القائمة.

## Submission

Copy `SUBMISSION-NOTES.txt` into the form. Attach the ZIP or PDF. APK is inside the ZIP because the earlier form does not list direct APK uploads. Verify the current Week 2 form accepts the same formats and limits.
