# vote
Vote from calling it from javascript


document.getElementById('vote-support').addEventListener('click', function(){ vote(true);}, false);
document.getElementById('vote-against').addEventListener('click', function(){ vote(false);}, false);



# trueparameter and false parameter simply: 

Function vote() {
    ethervote.vote(proposalHash, support, {from: web3.eth.accounts[0]});
}


# “Ethervote” is the object we created before, and “vote” is one of its functions

function vote(bytes32 proposalHash, bool pro) {

# for make sure that the two parameters demanded by the function are working correctly we have to add a third object containing transaction informations,  this would generate a panel asking the user to confirm the transaction 

function vote(support) {
 
     web3.eth.getAccounts(function(e,accounts){
        // Check if there are accounts available
        if (!e && accounts && accounts.length > 0) {
            // Create a dialog requesting the transaction
            ethervote.vote(proposalHash, support, {from: accounts[0]})

          } else {
            mist.requestAccount(function(e, account) {
                if(!e) {
                    // Create a dialog requesting the transaction
                    ethervote.vote(proposalHash, support, {from: account.toLowerCase()})
                }
            });
        }
    });

}




