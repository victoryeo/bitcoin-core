# bitcoin-core
This is a customised bitcoin core. The changes are listed below:

1. In chainparamsbase.cpp, the nRPCPort is changed.

2. In chainparams.cpp, the nDefaultPort is changed.

3. In chainparams.cpp, the message signature is changed. 
pchMessageStart[0] = 0xf0;
pchMessageStart[1] = 0xb0;
pchMessageStart[2] = 0xb0;
pchMessageStart[3] = 0xd0;

4. In chainparams.cpp, the address prefix is changed.
base58Prefixes[PUBKEY_ADDRESS] = std::vector<unsigned char>(1,75)

5. In chainparams.cpp, the minimum chain work is changed to accelerate mining.
consensus.nMinimumChainWork = uint256S("0000000000000000000000000000000000000000000000000000000100010001");

6. In chainparams.cpp, the DNS seeds are removed
comment out the line: vSeeds.emplace_back

7. In chainparams.cpp, the genesis message is changed.
const char* pszTimestamp = "xxxxxx........";

8. The maximum block size is changed.
In consensus/consensus.h, changed from 400000 to 800000, this will give you 2M size block
static const unsigned int MAX_BLOCK_WEIGHT = 8000000

9. The block interval is changed.
In chainparams.cpp
Modify the nPowTargetSpacing from 10*60 to 1*60
