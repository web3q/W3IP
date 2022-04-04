---
w3ip: 4
title: NFT with On-Chain Metadata
author: Qi Zhou (@qizhou)
discussions-to: TBD
status: Draft
type: Standards Track
category: ERC
created: 2022-04-04
requires: 721, 1155
---

interface
```
interface NFTOnChainMetadata {
    // @notice Read the metatdata using _tokenId.
    // @dev Throws if `_tokenId` is not a valid NFT.
    function readMetadata(uint256 _tokenId) external view returns (bytes memory);
    
    // @notice Get the metatdata using _tokenInfo.  
    // @dev The tokenInfo should be in the format of "tokenId.type".  For example, when the metadata is an JPEG file, then
    // the type should be "jpg". This will help the Web3 URL to identify MIME type of the metadata according W3IP-1.
    // Throws if `tokenId` is not a valid NFT.
    function getMetadata(bytes memory _tokenInfo) external view returns (bytes memory);
}
```

The interface can be used by NFT721 and NFT1155 directly.