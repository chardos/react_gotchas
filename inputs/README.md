#React input gotchas

##Updating values that are passed in from props
- Props passed in through `getInitialState` will not update automatically.
- Need a `componentWillReceiveProps` method to keep passing the props in to the values.

``` jsx
  //Note: On subsequent rerenders this will not update the input values
  getInitialState: function() {
    return {
      titleValue: this.props.note.title,
      descValue: this.props.note.description
    };
  },

  //Note: This method is needed to keep the props in a current state.
  componentWillReceiveProps: function(nextProps) {
    this.setState({
      titleValue: nextProps.note.title,
      descValue: nextProps.note.description
    });
  },
  render: function(){
    return(
      <div className="Release-edit-single-wrap">
        <select className="Release-edit-select" name="">
          <option value="Feature">Feature</option>
          <option value="Bug">Bug</option>
        </select>
        <div className="Release-edit-input-wrap">
          <input type="text" className="Release-edit-title" placeholder={this.props.note.title} valueLink={this.linkState('titleValue')} />
          <input type="text" className="Release-edit-description" placeholder="Description" valueLink={this.linkState('descValue')} />
        </div>
        <div className="Release-edit-delete shipyard-icon-cross" onClick={this.deleteNote.bind(this, this.props.i)}></div>
      </div>
    )
  }
`
