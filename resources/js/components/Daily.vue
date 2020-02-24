<template>
    <div class="container">
      <div class="row">
        <div class="col-md-12">
          <div class="card">
            <div class="card-header with-border">
              <h3 class="card-title mt-2">Daily Summary</h3>
              <div class="card-tools pull-right">
                <button class="btn btn-success mt-2" data-toggle="modal" data-target="#newEntry"><i class="fas fa-plus"></i> New Entry</button>                            
              </div>
            </div>
            <!-- /.card-header -->
            <div class="card-body table-responsive no-padding">
              <table class="table table-bordered table-hover">
                <tbody>
                  <tr>
                    <th>Date</th>
                    <th>Time</th>
                    <th>Plate Number</th>
                    <th>Truck Code</th>                    
                    <th>Action Taken</th>
                    <th>Modify</th>
                  </tr>
                  <tr>
                    <td>February 12, 2020</td>
                    <td>11:42 AM</td>
                    <td>ABK 6580</td>
                    <td>12</td>
                    <td>Apprehended</td>
                    <td>
                      <a href="#" title="Edit">
                        <i class="fa fa-edit orange-icon"></i>
                      </a>                    
                      <a href="#" title="View Info">
                        <i class="fa fa-eye orange-icon"></i>
                      </a>
                    </td>
                  </tr>
                </tbody>
              </table>
            </div>
            <!-- /.card-body -->
          </div>
          <!-- /.card -->
        </div>
      </div>    
      <!-- Modal -->
      <div class="modal fade bd-example-modal-lg" id="newEntry" tabindex="-1" role="dialog" aria-labelledby="newEntryTitle" aria-hidden="true">
        <div class="modal-dialog modal-lg modal-dialog-centered" role="document">
          <div class="card modal-content">
            <div class="card-header modal-header">
              <h5 class="modal-title" id="newEntryTitle">Daily Entry</h5>
              <button type="button" class="close" data-dismiss="modal" aria-label="Close">
                <span aria-hidden="true">&times;</span>
              </button>
            </div>
            
            <div role="tabpanel">
              <!-- Nav tabs -->
              <ul class="nav nav-tabs" role="tablist">
                  <li role="presentation" class="nav-item">
                    <a href="#general" class="nav-link active" aria-controls="general" role="tab" data-toggle="tab">General Information</a>
                  </li>
                  <li role="presentation" class="nav-item">
                    <a href="#weight" class="nav-link" aria-controls="weight" role="tab" data-toggle="tab">Vehicle Load Information</a>
                  </li>
              </ul>
            </div>
            <div class="card-body modal-body">
              <!-- Tab panes -->
              <div class="tab-content">
                  <div role="tabpanel" class="tab-pane active" id="general">
                    <div class="row mt-2">
                      <div class="col-md-12">
                        <form class="form-horizontal" role="form">
                          <fieldset>
                            
                            <!-- General Info -->
                            <div class="row">
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="date">Date</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="time">Time</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                            </div>
                            <div class="row">
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="plate_number">Plate Number</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="truck_code">Truck Code</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                            </div>
                            <div class="row">
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-10 control-label" for="allowable_gvw">Allowable Gross Vehicle Weight</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="commodity">Commodity Carried</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                            </div>
                            <div class="row">
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="origin">Route Origin</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-6">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="destination">Route Destination</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                            </div>           

                          </fieldset>
                        </form>
                      </div><!-- /.col-lg-12 -->
                    </div><!-- /.row -->  
                  </div>
                  <div role="tabpanel" class="tab-pane" id="weight">
                    <div class="row mt-2">
                      <div class="col-md-12">
                        <form class="form-horizontal" role="form">
                          <fieldset>
                            
                            <!-- General Info -->
                            <div class="row">
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-4 control-label" for="axle1">Axle 1</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-4 control-label" for="axle2">Axle 2</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-4 control-label" for="axle3">Axle 3</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                            </div> 
                            <div class="row">
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-4 control-label" for="axle4">Axle 4</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-4 control-label" for="axle5">Axle 5</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-4 control-label" for="axle6">Axle 6</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                            </div>
                            <div class="row">
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-6 control-label" for="total_gvw">Total GVW</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-8 control-label" for="axle_overload">Axle Overload</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                              <div class="col-md-4">
                                <div class="form-group">
                                  <label class="col-sm-8 control-label" for="gvw_overload">GVW Overload</label>
                                  <div class="col-sm-12">
                                    <input type="text" class="form-control">
                                  </div>
                                </div>
                              </div>
                            </div>                                           

                          </fieldset>
                        </form>
                      </div><!-- /.col-lg-12 -->
                    </div><!-- /.row -->  
                  </div>
              </div>                    
            </div>
            <div class="modal-footer">
              <button type="button" class="btn btn-danger" data-dismiss="modal">Cancel</button>
              <button type="button" class="btn btn-primary">Add Entry</button>
            </div>
          </div>
        </div>
      </div>

    </div>
</template>

<script>
    export default {


        mounted() {
            console.log('Component mounted.')
        }
    }
</script>
