---


copyright:
  years: 2018
lastupdated: "2018-07-24"


---

# About {{site.data.keyword.dsfm_full_notm}}
{: #about-data-store-for-memcache}

{{site.data.keyword.dsfm_full}} Service provides a managed memcache service in the IBM Cloud that provides Non-Volatile Memory-based object caching to accelerate cloud applications.
Cloud applications extensively use DRAM-based caching solutions, like [Memcached](http://memcached.org/), to accelerate their workloads (e.g., [drupal](https://www.drupal.org/project/memcache), [wikipedia](http://www.datacenterknowledge.com/archives/2008/06/24/a-look-inside-wikipedias-infrastructure), [reddit](https://redditblog.com/2017/01/17/caching-at-reddit/), etc., transparently use memcache).
{{site.data.keyword.dsfm_short_notm}} replaces DRAM with modern NVM storage for caching using the same memcache API, offering orders of magnitude higher capacity, at a lower cost, while maintaining performance.

## API

{{site.data.keyword.dsfm_short_notm}} implements the ascii [memcache protocol](https://github.com/memcached/memcached/blob/master/doc/protocol.txt).

## Instructions to setup a {{site.data.keyword.dsfm_short_notm}} client (ubuntu)

1. Download {{site.data.keyword.dsfm_short_notm}} client setup script:
```
git clone git@github.com:ibm-research/data-store-for-memcache-client.git;
cd data-store-for-memcache-client
```
2. Install dependencies:
```
sudo apt-get install stunnel4
pip install -r requirements.txt
```
3. Run {{site.data.keyword.dsfm_short_notm}} client configuration script (your specific instance crn will be provided at your service instance's dashboard):
```
python python/client.py --apikey <your-ibm-cloud-api-key> --instance_crn <your-service-instance-crn>
```
4. If everything went smoothly, you should be able to start your memcache client with the endpoint set to localhost:11211
