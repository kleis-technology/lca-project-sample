# LCA Project Sample

This is a sample project to show case the LCA DSL and the associated [IntelliJ plugin](https://plugins.jetbrains.com/plugin/20543-life-cycle-analysis-as-code).

<!-- Plugin description -->
Adds support for a new domain-specific language targeting <i>Life Cycle Analysis</i> experts. The following features are available for free.
<ul>
    <li>EF 3.1 flows and characterization factors from the <a href="https://eplca.jrc.ec.europa.eu/LCDN/developerEF.xhtml">European Platform on Life Cycle Assessment</a></li>
    <li>Description of processes, intermediary and elementary flows, with parameters.</li>
    <li>Embedded inventory computation engine.</li>
    <li>Code navigation.</li>
</ul>
<!-- Plugin description end -->

## Installation

- Using IDE built-in plugin system:
  - <kbd>Settings/Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>Marketplace</kbd> > <kbd>Manage plugin repositories</kbd> > <kbd> Add `https://plugins.jetbrains.com/plugins/alpha/list` </kbd>
  - <kbd>Settings/Preferences</kbd> > <kbd>Plugins</kbd> > <kbd>Marketplace</kbd> > <kbd>Search for "life cycle analysis as code"</kbd> >
    <kbd>Install Plugin</kbd>
  

---


## LCA File type example


```lca
package carrot

import ef31.*

process carrot_production {
    parameters {
        - R1: 2.0
        - qElec : 3.0
    }

    products {
        - carrot 1 kg
    }

    inputs {
        - electricity ${qElec} kJ
        - water ${3.0} l
    }

    emissions {
        - "HFC-32, air, lower stratosphere and upper troposphere" ${2 * sin(R1)^2 + qElec^2} kg
        -  "warfarin, air, non-urban high stack" 3 kg
    }
}

process electricity_production {
    products {
        - electricity 1 kJ
    }

    emissions {
        - "(+)-bornan-2-one, air, urban air close to ground" 1.0 kg
    }
}

process water_production {
    products {
        - water 1 l
    }

    emissions {
        - "HFC-23, soil, agricultural" 1 kg
        - "HFC-32, air, lower stratosphere and upper troposphere" 1 kg
    }
}
```

