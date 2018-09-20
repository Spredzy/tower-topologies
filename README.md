# Tower Topology

Tower Topology offers a list of know-to-work deployment topology.
It relies on [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) in order to provide those scenario in some cloud agnostic way.

## Scenarios

* `topologies/allinone`
* `topologies/single_tower_database`
* `topologies/cluster_tower_database`
* `topologies/cluster_tower_database_haproxy`

## Usage

### Infrastructure Deployment

First, one needs to retrieve the [ansible-cloud](https://github.com/redhat-cip/ansible-cloud) project and clone this project
within it.

```bash
#> git clone https://github.com/redhat-cip/ansible-cloud
#> git clone https://github.com/Spredzy/tower-topologies ansible-cloud/tower
```

Then run the following command:

```bash
#> ANSIBLE_CLOUD_PROVIDER=openstack ansible-playbook -i inventory/hosts cloud.yml -e @tower/topologies/allinone/topology.yml
```

### Application deployment

Make sure your environment is setup to use the proper dynamic inventory you'd be using - here openstack.

```bash
#> cd tower/deployment
#> ansible-playbook -i openstack.yml install.yml
```

Done.

## Contact

  * Yanis Guenane  <yguenane@redhat.com>

## License

  * Apache 2.0
