# Glance

## Icon sources:

 - di: => https://icons.homarr.dev/
 - si: => https://simpleicons.org/

## Monitor-Listen auf der HomeLab-Seite

Die Monitor-Widgets in `templates/homelab.yml.j2` werden automatisch erzeugt
aus allen `proxy:`-Einträgen in `host_vars`, die einen `dashboard:`-Block haben:

```yaml
proxy:
  - name: bazarr
    hostname: 'bazarr.berger-em.net'
    proxy_host: 'http://{{ host_ip }}:6767'
    dashboard:
      group: Servarr          # muss in glance_monitor_groups stehen
      title: Bazarr
      icon: 'di:bazarr'
      # url: https://...      # optional, Default: https://<hostname>
      # alt_status_codes: [401, 403]
```

Dienste ohne eigenen Proxy-Eintrag stehen in `glance_extra_sites`
(`defaults/main.yml`). Sortierung innerhalb einer Gruppe: alphabetisch nach Titel.
