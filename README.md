# Jenkins Packer Files for Master and Workers
This is the repository for jenkins packer files used to create an AMI for jenkins master and workers.

### Why Packer?
Packer is an open source tool for creating identical machine images for multiple platforms from a single source configuration. It brings pre-baked images into the modern age, improves the agility of the operations team, makes image creation less tedious and a lot easier to manage.
#### Advantages
- Super fast infrastructure deployment
- Multi-provider portability
- Improved stability
- Greater testability

#### How do I Packer?
It depends on your needs and target setup. In this case, we will be using Packer in creating automation scripts AMIs that will be used for our automation efforts accross different VPCs.

AMIs are regional. Its accessability doesn't depend on the VPC where it was created.

#### Required softwares
 - Packer v1.3.5
 - Git
 - Jenkins 2.164 (Not needed if Packer is ran locally)

#### Sample Usage:
For Master<br />
`packer build jenkins-master/packerfile.json`<br />
For Workers<br />
`packer build jenkins-slave/maintenance-scripts/packerfile.json`<br />
