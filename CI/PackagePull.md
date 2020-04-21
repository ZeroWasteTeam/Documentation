# Access Github packages from Workstation

* You must use a personal access token with the appropriate scopes to publish and install packages in GitHub Packages.
* To keep your credentials secure, we recommend you save your personal access token in a local file on your computer and use  Docker's --password-stdin flag, which reads your token from a local file. Use either of below Commands


   * $ cat ~/TOKEN.txt | docker login docker.pkg.github.com -u USERNAME --password-stdin 
                              
    * docker login docker.pkg.github.com -u chakithxxx --password 3xxxxx     (password : Token, recommended for windows)
    
    
    How to generate a token  ?  check [here](https://help.github.com/en/packages/publishing-and-managing-packages/about-github-packages#about-tokens)
    
                           
        
    
