1. **python** - top 3 books to learn python (IMHO)
    * [python Essential Reference 4ed by David Beazley](http://www.dabeaz.com/per.html)
    * [python cookbook by David Beazley](http://www.dabeaz.com/cookbook.html)
    * [Fluent Python by Luciano Ramalho](http://shop.oreilly.com/product/0636920032519.do)
2. **pytest** - learning resources
    * [pytest-doc](https://docs.pytest.org/en/latest/)
    * [quick overview](http://www.pydanny.com/pytest-no-boilerplate-testing.html)
    * [3 hours training on pytest](https://www.youtube.com/watch?v=AiThU6JQbE8)
    * [Advance fixtures training](https://www.youtube.com/watch?v=dYpfIz219vs)
    * [various other talks](http://pytest.org/latest/talks.html)
    * [python testing with pytest](https://pragprog.com/book/bopytest/python-testing-with-pytest)
3. **most important mvtest APIs**
    * [ExpectShell API](https://montavista-opensourcetechnology.github.io/mvtest/_modules/apis/utils.html#ExpectShell) for interactive testing
    * [RemoteMachine API](https://montavista-opensourcetechnology.github.io/mvtest/_modules/apis/utils.html#RemoteMachine) for running commands on remote host
    * [run_cmd API](https://montavista-opensourcetechnology.github.io/mvtest/_modules/apis/utils.html#run_cmd) for running commands locally
    * [get_status_output API](https://montavista-opensourcetechnology.github.io/mvtest/_modules/apis/utils.html#get_status_output) if command exit status and output is needed.
4. **custom logging levels**  
    mvtest uses following [custom logging levels](https://docs.python.org/2/howto/logging.html)  
    * _log.command_ for COMMAND logging
    * _log.texitcode_ for EXIT_CODE logging
    * _log.output_ for OUTPUT logging
    * _log.tpass_ for PASS logging
    * _log.tfail_ for FAIL logging
