# Homepage visitor statistics

The Statistics section uses a free, dedicated Flag Counter created on
2026-09-23. No server, subscription, email registration, or API key is needed.

- Counter ID: `cqzj` on `s01.flagcounter.com`.
- Public country statistics: https://info.flagcounter.com/cqzj
- World map: https://s01.flagcounter.com/map/cqzj/size_l/txt_333333/border_FFFFFF/pageviews_1/viewers_0/flags_1/
- Provider documentation: https://www.flagcounter.com/faq.html

## How it works

The browser requests the map directly from Flag Counter over HTTPS. This
request lets the provider infer a country from the visitor's IP and record
the visit. The homepage shows the map, number of countries, and page views;
the linked statistics page provides the country breakdown. This integration
does not provide a private dashboard of individual IP addresses.

Only one counter image is embedded. It loads eagerly so a visitor need not
scroll to Statistics to be counted. Do not add a second counter image just
to show a separate total: each image load contributes to page views.

The provider normally counts a repeat visitor again after 24 hours. Its
embedded image can lag behind the statistics page by about five minutes.
VPNs and proxies can cause the country to reflect the network exit location.
Implementation checks have already contributed an initial test visit. The
provider may need up to 48 hours to populate all reports for a new counter.

The map is responsive and needs no third-party JavaScript or map tiles.
Local inline JavaScript shows an unavailable message on an image error, a
1-pixel placeholder, or after 12 seconds, and restores the map if a slow
request eventually succeeds.
The image still works with JavaScript disabled.

## Availability and maintenance

The new map and public details page returned HTTP 200 during setup. A
Globalping check at 2026-09-23 03:35 UTC also fetched the provider's sample
map from six nodes. All returned HTTP 200, `image/png`, with verified TLS:

| Location | Network | Total request time |
| --- | --- | --- |
| Xi'an, China | China Telecom, AS4134 | 839 ms |
| Guilin, China | China Unicom, AS4837 | 895 ms |
| Xi'an, China | China Mobile, AS9808 | 1042 ms |
| Los Angeles, USA | HostPapa | 267 ms |
| Falkenstein, Germany | Hetzner | 789 ms |
| Singapore | LeaseWeb | 970 ms |

Measurement ID: `2clp0761A1w3titQz00021Bax`.
Result: https://api.globalping.io/v1/measurements/2clp0761A1w3titQz00021Bax
(the external result may expire).

The probes requested the service's official sample counter `88` with its
normal `https://www.flagcounter.com/` referrer, so these tests did not add
visitors to the homepage counter. The sample requires that referrer: an
initial request without it returned a redirect to an invisible placeholder
on all six networks. The homepage counter separately returned an 800 x 375
PNG with the homepage referrer.

These checks establish service reachability at that time, rather than
guaranteeing every visitor's browser, the GitHub Pages site itself, or
worldwide availability. Failed or blocked image requests cannot be counted,
and this installation has no independent backup collector.

The provider's free service may remove counters with no new visitor for
over 30 days. Keep the counter ID and URLs above for reference. This counter
was created using the provider's optional-registration Skip flow, so there
is no email login or account-management password.

These are new statistics, separate from the previous MapMyVisitors and
Busuanzi counts. No historical data has been imported. The former map
script is retained here for reference:

https://mapmyvisitors.com/map.js?d=GAPcigH5pSNjrFnZ8HxvmT3felQ-P7aHr1Wg42oH5s8&cl=ffffff&w=a

The previous total used the `busuanzi_value_site_pv` element and
https://busuanzi.ibruce.info/busuanzi/2.3/busuanzi.pure.mini.js . Both old
embeds have been removed from the homepage.

Publish the updated `index.html` through the repository's normal GitHub
Pages workflow. Creating the counter and editing the local page do not
publish the page automatically.
