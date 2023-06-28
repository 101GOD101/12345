    function mintMonkeys(uint numberOfTokens) public payable {
        require(saleIsActive, "Sale must be active to mint Monkeys");
        require(numberOfTokens <= maxPurchase, "Can only mint 10 tokens at a time");
        require(totalSupply().add(numberOfTokens) <= MAX_MONKEYS, "Purchase would exceed max supply of Monkeys");
        require(_monkeyPrice.mul(numberOfTokens) <= msg.value, "Ether value sent is not correct");
        
        for(uint i = 0; i < numberOfTokens; i++) {
            uint mintIndex = totalSupply();
            if (totalSupply() < MAX_MONKEYS) {
                _safeMint(msg.sender, mintIndex);
