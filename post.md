## Test Post

<div class="tab-container">
<ul class="nav nav-pills mb-3" id="pills-tab" role="tablist">
  <li class="nav-item" role="presentation">
    <button class="nav-link active" id="pills-home-tab" data-bs-toggle="pill" data-bs-target="#pills-home" type="button" role="tab">code-1.sol</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="pills-profile-tab" data-bs-toggle="pill" data-bs-target="#pills-profile" type="button" role="tab">code-2.sol</button>
  </li>
  <li class="nav-item" role="presentation">
    <button class="nav-link" id="pills-contact-tab" data-bs-toggle="pill" data-bs-target="#pills-contact" type="button" role="tab">expample.sol</button>
  </li>
</ul>
<div class="tab-content" id="pills-tabContent">
  <div class="tab-pane fade show active" id="pills-home" role="tabpanel">
<pre><code class="language-solidity">contract Implementation {
    event Result(uint256 newValue);

    function addNumbers(uint256 number1, uint256 number2) public returns (uint256 result ) {
        result = number1 + number2;
        emit Result(result);
    }
}</code></pre>
</div>
  <div class="tab-pane fade" id="pills-profile" role="tabpanel"><pre><code class="language-solidity">// SPDX-License-Identifier: MIT
pragma solidity 0.8.25;

contract Proxy {
    // Change the implementation address to the one you get after deploying the
    // implementation contract
    address immutable implementation = 0x44fE319Fc0C2d3e09F9a86AF94eEabB6173A1d58;

    fallback(bytes calldata data) external returns (bytes memory) {
        (bool success, bytes memory result) = implementation.delegatecall(data);
        require(success, "Delegatecall failed");
        return result;
     }
}</code></pre></div>
  <div class="tab-pane fade" id="pills-contact" role="tabpanel">...</div>
</div>
</div>
