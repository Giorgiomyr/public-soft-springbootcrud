<template>
  <el-dialog type="warning" title="Διαχείριση Supplier" :visible="visible" :modal="true"
             :close-on-click-modal="false"
             :close-on-press-escape="false" :modal-append-to-body="false" :show-close="false" width="75%"
             @close="clearValidation">

    <el-card>
    <el-form ref="supplierForm" :model="Supplier" :rules="rules" label-position="top">

      <el-row :gutter="20">
        <!-- LEFT COLUMN -->
        <el-col :span="12">

          <el-form-item label="Εισάγετε το όνομα της εταιρείας"
                        prop="companyname">
            <el-input prefix-icon="fa fa-user"
                      v-model="supplier.companyName"
                      placeholder="όνομα της εταιρείας"
                      autoComplete="companyname">
            </el-input>
          </el-form-item>

          <el-form-item label="Εισάγετε το όνομα σας"
                        prop="fname">
            <el-input prefix-icon="fa fa-phone"
                      v-model="supplier.firstName"
                      placeholder="Όνομα"
                      autoComplete="fname">
            </el-input>
          </el-form-item>
          <el-form-item label="Εισάγετε το επίθετο σας"
                        prop="lname">
            <el-input prefix-icon="fa fa-phone"
                      v-model="supplier.lastName"
                      placeholder="Επίθετο"
                      autoComplete="lname">
            </el-input>
          </el-form-item>

          <el-form-item label="Εισάγετε το ΑΦΜ σας"
                        prop="vat">
            <el-input prefix-icon="fa fa-envelope"
                      v-model="supplier.vatNumber"
                      type="vat"
                      placeholder="ΑΦΜ"
                      autoComplete="vat">
            </el-input>
          </el-form-item>

        </el-col>

        <!-- RIGHT COLUMN -->
        <el-col :span="12">

          <el-form-item label="Εισάγετε την Εφορία σας"
                        prop="irs">
            <el-input prefix-icon="fa fa-envelope"
                      v-model="supplier.irsOffice"
                      type="irs"
                      placeholder="Εφορία"
                      autoComplete="irs">
            </el-input>
          </el-form-item>

          <el-form-item label="Εισάγετε τη Διεύθυνση σας"
                        prop="address">
            <el-input prefix-icon="fa fa-envelope"
                      v-model="supplier.address"
                      type="address"
                      placeholder="Διεύθυνση"
                      autoComplete="address">
            </el-input>
          </el-form-item>

          <el-form-item label="Εισάγετε την Πόλη σας"
                        prop="city">
            <el-input prefix-icon="fa fa-envelope"
                      v-model="supplier.city"
                      type="city"
                      placeholder="Πόλη"
                      autoComplete="city">
            </el-input>
          </el-form-item>

          <el-form-item label="Εισάγετε τη Χώρα σας"
                        prop="country">
            <el-input prefix-icon="fa fa-envelope"
                      v-model="supplier.country"
                      type="country"
                      placeholder="Χώρα"
                      autoComplete="country">
            </el-input>
          </el-form-item>

          <el-form-item prop="active">
            <template>
              <el-checkbox v-model="supplier.active">Ενεργό</el-checkbox>
            </template>
          </el-form-item>

        </el-col>
      </el-row>

    </el-form>

      <el-row>
        <el-col style="text-align: right">
          <el-button type="success"
                     icon="fa fa-save"
                     @click="save"> Αποθήκευση </el-button>

          <el-button type="danger"
                     icon="fa fa-remove"
                     @click="confirmDelete"
                     :disabled="!isDeletable"> Διαγραφή </el-button>
        </el-col>
      </el-row>
    </el-card>

    <div slot="footer" class="dialog-footer card-footer">
      <el-button type="warning"
                 icon="el-icon-back"
                 @click="cancel"> Επιστροφή </el-button>
    </div>

  </el-dialog>
</template>
<script src="./SupplierVM.js"></script>\n
