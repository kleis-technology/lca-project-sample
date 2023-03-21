# LCA Project Sample

This is a sample project to show case the LCA DSL and the associated [IntelliJ plugin](https://plugins.jetbrains.com/plugin/20543-life-cycle-analysis-as-code).

<!-- Plugin description -->
Adds support for a new domain-specific language targeting <i>Life Cycle Analysis</i> experts.
The following features are available :
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

process carrot_production {
    params {
        qElec = 3.0 kJ
    }

    products {
        1 kg carrot
    }

    inputs {
        qElec electricity
        3 l water
    }

    emissions {
        (57 percent*kg/kJ) * Qelec co2
    }
}

process electricity_production {
    products {
        1 kJ electricity
    }

    emissions {
        1.0 kg co2
    }
}
```

