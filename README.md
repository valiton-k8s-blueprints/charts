# Blueprint Helm Charts

This repostory contains helm charts used by the Kubernetes blueprint.
These are either charts where no official chart is available or charts 
for blueprint specific purposes (e.g. create an ACME ClusterIssuer for
cert-manager).

Charts that apply only to a certain cloud provider are placed in the respective 
subdirectory.

## Usage

[Helm](https://helm.sh) must be installed to use the charts. Please refer to
Helm's [documentation](https://helm.sh/docs) to get started.

Once Helm has been set up correctly, add the repo as follows:

    helm repo add blueprint-charts valiton-k8s-blueprints.github.io/charts

If you had already added this repo earlier, run `helm repo update` to retrieve
the latest versions of the packages.  You can then run `helm search repo
{alias}` to see the charts.
