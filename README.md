<div align="center">
  <a href="https://exchange.blockchain.com/?utm_campaign=expmarketing_getstarted">
    <picture>
      <source media="(prefers-color-scheme: dark)" srcset="https://exchange.blockchain.com/?utm_campaign=expmarketing_getstarted">
      <img alt="Blockchain logo" src="https://exchange.blockchain.com/?utm_campaign=expmarketing_getstarted">
    </picture>
  </a>
  <h3>Reference implementation of Live Chart, news and tools</h3>
  <hr/>
</div>
00 -5673,6 +5673,26 CO td: :Status TonlibClient:: do_request (const tonlib_api::blocks_lookupBlock& reques td:: Status
check_lookup_block_proof(lite_api_ptr<ton::1
ite_api: :liteServer_lookupBlockResult>&
result, int mode, ton::BlockId blkid, ton: :BlockIdExt client_mc_blkid, td::uint64
It, td::uint32 utime) {
try {
ton: :BlockIdExt cur_id =
ton: :create_block_id(result->mc_block_id_);
if (Icur_id. is_masterchain_ext()) {
+
return td::Status::Error("invalid
response: mc block id is not from masterchain");
+
}
+
if (client_mc_blkid != cur_id) {
+
auto state =
block::check_extract_state_proof(client_m-c_ blkid, result-
›client_mc_state_proof_.as_slice(),
+ result->mc_block_proof_.as_slice());