# Ask Dad

The McAdoo family's unblock-request page, live at https://ask.macdwellings.com.

Control D's branded block page (on the kids' and Home profiles) has an "Ask Dad" /
"Ask Jeremy" button that opens this page as:

```
https://ask.macdwellings.com/?who=emma&site={domain}
```

`who` is one of `bennett`, `emma`, `sophia`, `home`. Control D fills `{domain}` with
the blocked site. The page takes a short reason and posts to the `ask-dad` Supabase
edge function (Bible Study project), which logs the request in
`public.ask_dad_requests` and sends Jeremy an ntfy push notification.

- `logos/` are also the Control D block page logos (each profile's Logo URL points here).
- The ntfy channel name lives only in the edge function, never in this repo.
- Static site served by GitHub Pages from `main`, root folder.
