# Error pages
These are the error pages for my various services. They are all written as self-contained HTML files, and are designed to be as simple as possible. They utilize Caddy's [templating features](https://caddyserver.com/docs/caddyfile/directives/templates)

<div align="center">
    <!-- ![screenshot](https://github.com/user-attachments/assets/94e44ec7-8cd4-4b7e-9a73-8c134eab9a60) -->
    <img src="https://github.com/user-attachments/assets/94e44ec7-8cd4-4b7e-9a73-8c134eab9a60" alt="screenshot demo">
</div>

## Usage
Simply point to the pages in your web server configuration, and you're good to go.

Example:
```Caddyfile
# Manual handling
handle_errors 5xx {
    root * /path/to/error-pages/borked
    rewrite * /index.html
    vars template_message "Your custom message can go here"
    templates
    file_server {
        status 500 # You might want to change this for specific error codes.
    }
}
```

## License
These error pages are licensed under the GPL-3.0 license. You can find the full text of the license in the `LICENSE` file.
