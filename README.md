# X-skirtor

X-ray torus models for the microcalorimeter era. Calculated with [SKIRT](https://ui.adsabs.harvard.edu/abs/2023A%26A...674A.123V).

## I. X-skirtor_smooth: A smooth torus model for XRISM/Resolve

X-skirtor_smooth is the first X-ray torus model calculated with the SKIRT code, modelling X-ray reprocessing by cold gas.

<table>
  <tr>
    <td><img src="Torus_sketch.png" alt="Smooth torus geometry showing the free model parameters" width="400"/></td>
    <td><img src="TopRightZoomOnly.png" alt="Example spectrum showing the various lines, the Fe Ka Compton hump, and absorption edges" width="400"/></td>
  </tr>
  <tr>
    <td align="center"><strong>Torus Geometry</strong><br/>Smooth torus geometry showing the free model parameters<br/>Observed at inclination i</td>
    <td align="center"><strong>Spectral Features</strong><br/>Example spectrum showing the various lines, the Fe Ka <br/>Compton hump, and absorption edges</td>
  </tr>
</table>

### Getting started:

#### 1. Download the model

[📥 xskirtor_smooth_xrism](https://sron365-my.sharepoint.com/:u:/g/personal/b_vander_meulen_sron_nl/IQACzE10-7LsT4I2wtFzUWb8AWlHEXdOq-q2qqIefNeGqV4) — Suited for XRISM/Resolve data, with an adaptive energy resolution (1.5–15 keV)

[📥 xskirtor_smooth_ccd](https://sron365-my.sharepoint.com/:u:/g/personal/b_vander_meulen_sron_nl/IQCXli9pZkjgR64Pp1VdN7PhAR-32zEqrzVqxwOfJCjsGWE) — Suited for broadband CCD data, with a spectral resolution of R=433 (0.2–200 keV)

#### 2. Load in XSPEC
X-skirtor_smooth is provided as an XSPEC table model, which can be loaded in XSPEC as:
```xspec
model atable{xskirtor_smooth_tot.mod}
```
which is exactly identical to:
```xspec
model atable{xskirtor_smooth_rpc.mod} + atable{xskirtor_smooth_dir.mod}
```
when the parameters of the reprocessed and direct (i.e. transmitted) flux components are tied.

The same tables are also supported by SPEX, SHERPA, ISIS.
