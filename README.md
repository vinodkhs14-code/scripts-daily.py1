
from datetime import datetime, timezone
from pathlib import Path
from zoneinfo import ZoneInfo
import json

PROJECT = "Starry Nest Stories"
OUTPUT = Path("output")
OUTPUT.mkdir(parents=True, exist_ok=True)

now = datetime.now(ZoneInfo("Asia/Kolkata"))

checkpoint = {
    "project": PROJECT,
    "date": now.strftime("%Y-%m-%d"),
    "time_ist": now.isoformat(),
    "status": "scheduler_test_passed",
    "story": "pending",
    "hd_scenes": "pending",
    "poster": "pending",
    "google_drive": "pending",
    "facebook": "pending"
}

checkpoint_file = OUTPUT / "checkpoint.json"

checkpoint_file.write_text(
    json.dumps(checkpoint, indent=2),
    encoding="utf-8"
)

print("=" * 45)
print("STARRY NEST STORIES - CLOUD TEST")
print("=" * 45)
print("Project:", PROJECT)
print("India time:", now.strftime("%d-%m-%Y %I:%M %p"))
print("Scheduler: SUCCESS")
print("Checkpoint:", checkpoint_file)
print("Google Drive: Not configured")
print("Facebook: Not configured")
print("=" * 45)
