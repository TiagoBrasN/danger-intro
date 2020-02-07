message("You have added 3 more gems to the app.")

# Ignoring warnings from Pods
xcode_summary.ignored_files = 'Pods/**'

# Ignoring specific warnings
xcode_summary.ignored_results { |result|
  result.message.start_with? 'ld' # Ignore ld_warnings
}

xcode_summary.report 'xcodebuild.json'

has_app_changes = !git.modified_files.empty?

# Add a CHANGELOG entry for app changes
if !git.modified_files.include?("CHANGELOG.md") && has_app_changes
  fail("Please include a CHANGELOG entry. \nYou can find it at [CHANGELOG.md](https://github.com/realm/jazzy/blob/master/CHANGELOG.md).")
  message "Note, we hard-wrap at 80 chars and use 2 spaces after the last line."
end
