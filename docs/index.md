---
layout: page
title: Listening examples
---

<div class="note">
Use headphones and keep the playback level moderate. The files below are
peak-normalized only for listening. Each STFT is normalized to its own
peak, while all panels use the same dB range. These examples provide a
qualitative comparison between generated impulse responses.
</div>

{% for example in site.data.examples %}
## Example {{ example.number }}

<table class="demo-table">
  <thead><tr><th>Conditioning</th><th>Ground truth</th><th>CLFM</th><th>W-CFM</th></tr></thead>
  <tbody><tr>
    <td class="parameters"><i>&mu;</i> = {{ example.mu }}<br><i>D</i>/<i>&mu;</i> = {{ example.D_mu }}<br><i>T</i><sub>0</sub>/<i>&mu;</i> = {{ example.T0_mu }}<br><i>L</i><sub>y</sub> = {{ example.Ly }} m<br><i>x</i><sub>o</sub> = {{ example.op_x }}<br><i>y</i><sub>o</sub> = {{ example.op_y }}</td>
    <td><audio controls preload="none"><source src="examples/{{ example.name }}/ground_truth.wav" type="audio/wav">Audio playback is not supported.</audio><div class="t60"><i>T</i><sub>60</sub> = {{ example.t60_gt }} s</div></td>
    <td><audio controls preload="none"><source src="examples/{{ example.name }}/clfm.wav" type="audio/wav">Audio playback is not supported.</audio><div class="t60"><i>T</i><sub>60</sub> = {{ example.t60_clfm }} s</div></td>
    <td><audio controls preload="none"><source src="examples/{{ example.name }}/w_cfm.wav" type="audio/wav">Audio playback is not supported.</audio><div class="t60"><i>T</i><sub>60</sub> = {{ example.t60_w_cfm }} s</div></td>
  </tr></tbody>
</table>

<div class="diagnostic-grid">
  <figure><img src="examples/{{ example.name }}/stft_gt.png" alt="Ground-truth STFT for Example {{ example.number }}"></figure>
  <figure><img src="examples/{{ example.name }}/stft_clfm.png" alt="CLFM STFT for Example {{ example.number }}"></figure>
  <figure><img src="examples/{{ example.name }}/stft_w_cfm.png" alt="W-CFM STFT for Example {{ example.number }}"></figure>
  <figure><img src="examples/{{ example.name }}/waveform_gt_clfm.png" alt="GT and CLFM waveforms for Example {{ example.number }}"></figure>
  <figure><img src="examples/{{ example.name }}/waveform_gt_w_cfm.png" alt="GT and W-CFM waveforms for Example {{ example.number }}"></figure>
</div>
{% endfor %}
