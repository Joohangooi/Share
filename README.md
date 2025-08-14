<EntityType Name="bop_webinar">
  <Key>
    <PropertyRef Name="bop_webinar_id" />
  </Key>
  <Property Name="bop_webinar_id" Type="number" Nullable="false" StoreGeneratedPattern="Identity" />
  <Property Name="bop_title_en" Type="nvarchar" Nullable="false" MaxLength="150" />
  <Property Name="bop_title_bm" Type="nvarchar" Nullable="false" MaxLength="150" />
  <Property Name="bop_title_ch" Type="nvarchar" Nullable="false" MaxLength="1000" />
  <Property Name="BOP_CREATEBY" Type="nvarchar" MaxLength="10" />
  <Property Name="BOP_CREATESTMP" Type="timestamp" />
  <Property Name="BOP_LASTEDITBY" Type="nvarchar" MaxLength="10" />
  <Property Name="BOP_LASTEDITSTMP" Type="timestamp" />
  <Property Name="BOP_APPROVER1" Type="nvarchar" MaxLength="10" />
  <Property Name="BOP_APPROVESTMP1" Type="timestamp" />
  <Property Name="BOP_APPROVER2" Type="nvarchar" MaxLength="10" />
  <Property Name="BOP_APPROVESTMP2" Type="timestamp" />
  <Property Name="BOP_PENDID" Type="nvarchar" MaxLength="20" />
  <Property Name="bop_status" Type="number" Nullable="false" />
</EntityType>

<EntityType Name="bop_webinar_session">
  <Key>
    <PropertyRef Name="bop_session_id" />
  </Key>
  <Property Name="bop_session_id" Type="number" Nullable="false" StoreGeneratedPattern="Identity" />
  <Property Name="bop_webinar_id" Type="number" Nullable="false" />
  <Property Name="bop_session_datetime" Type="timestamp" Nullable="false" />
  <Property Name="bop_language" Type="nvarchar" Nullable="false" MaxLength="2" />
  <Property Name="bop_status" Type="number" Nullable="false" />
</EntityType>

<EntityType Name="bop_webinar_submission">
  <Key>
    <PropertyRef Name="bop_submission_id" />
  </Key>
  <Property Name="bop_submission_id" Type="number" Nullable="false" StoreGeneratedPattern="Identity" />
  <Property Name="bop_user_name" Type="nvarchar" Nullable="false" MaxLength="100" />
  <Property Name="bop_id_type" Type="nvarchar" Nullable="false" MaxLength="10" />
  <Property Name="bop_id_no" Type="nvarchar" Nullable="false" MaxLength="12" />
  <Property Name="bop_mobile_no" Type="nvarchar" Nullable="false" MaxLength="15" />
  <Property Name="bop_email_address" Type="nvarchar" Nullable="false" MaxLength="50" />
  <Property Name="bop_find_source" Type="nvarchar" MaxLength="200" />
  <Property Name="bop_consent_agreed" Type="number" Nullable="false" />
  <Property Name="bop_bo_branchcode" Type="nvarchar" Nullable="false" MaxLength="10" />
  <Property Name="bop_createstmp" Type="timestamp" />
  <Property Name="bop_ip_address" Type="nvarchar" MaxLength="50" />
</EntityType>

<EntityType Name="bop_webinar_user_session">
  <Key>
    <PropertyRef Name="bop_user_submission_id" />
    <PropertyRef Name="bop_session_id" />
  </Key>
  <Property Name="bop_user_submission_id" Type="number" Nullable="false" />
  <Property Name="bop_session_id" Type="number" Nullable="false" />
</EntityType>

<!-- Associations -->
<Association Name="FK_bop_webinar_session_bop_webinar">
  <End Role="bop_webinar" Type="Self.bop_webinar" Multiplicity="1" />
  <End Role="bop_webinar_session" Type="Self.bop_webinar_session" Multiplicity="*" />
  <ReferentialConstraint>
    <Principal Role="bop_webinar">
      <PropertyRef Name="bop_webinar_id" />
    </Principal>
    <Dependent Role="bop_webinar_session">
      <PropertyRef Name="bop_webinar_id" />
    </Dependent>
  </ReferentialConstraint>
</Association>

<Association Name="FK_bop_webinar_user_session_submission">
  <End Role="bop_webinar_submission" Type="Self.bop_webinar_submission" Multiplicity="1" />
  <End Role="bop_webinar_user_session" Type="Self.bop_webinar_user_session" Multiplicity="*" />
  <ReferentialConstraint>
    <Principal Role="bop_webinar_submission">
      <PropertyRef Name="bop_submission_id" />
    </Principal>
    <Dependent Role="bop_webinar_user_session">
      <PropertyRef Name="bop_user_submission_id" />
    </Dependent>
  </ReferentialConstraint>
</Association>

<Association Name="FK_bop_webinar_user_session_session">
  <End Role="bop_webinar_session" Type="Self.bop_webinar_session" Multiplicity="1" />
  <End Role="bop_webinar_user_session" Type="Self.bop_webinar_user_session" Multiplicity="*" />
  <ReferentialConstraint>
    <Principal Role="bop_webinar_session">
      <PropertyRef Name="bop_session_id" />
    </Principal>
    <Dependent Role="bop_webinar_user_session">
      <PropertyRef Name="bop_session_id" />
    </Dependent>
  </ReferentialConstraint>
</Association>







<EntityType Name="bop_webinar">
  <Key>
    <PropertyRef Name="bop_webinar_id" />
  </Key>
  <Property Name="bop_webinar_id" Type="Decimal" Nullable="false" />
  <Property Name="bop_title_en" Type="String" Nullable="false" MaxLength="150" />
  <Property Name="bop_title_bm" Type="String" Nullable="false" MaxLength="150" />
  <Property Name="bop_title_ch" Type="String" Nullable="false" MaxLength="1000" />
  <Property Name="BOP_CREATEBY" Type="String" MaxLength="10" />
  <Property Name="BOP_CREATESTMP" Type="DateTime" />
  <Property Name="BOP_LASTEDITBY" Type="String" MaxLength="10" />
  <Property Name="BOP_LASTEDITSTMP" Type="DateTime" />
  <Property Name="BOP_APPROVER1" Type="String" MaxLength="10" />
  <Property Name="BOP_APPROVESTMP1" Type="DateTime" />
  <Property Name="BOP_APPROVER2" Type="String" MaxLength="10" />
  <Property Name="BOP_APPROVESTMP2" Type="DateTime" />
  <Property Name="BOP_PENDID" Type="String" MaxLength="20" />
  <Property Name="bop_status" Type="Decimal" Nullable="false" />
</EntityType>

<EntityType Name="bop_webinar_session">
  <Key>
    <PropertyRef Name="bop_session_id" />
  </Key>
  <Property Name="bop_session_id" Type="Decimal" Nullable="false" />
  <Property Name="bop_webinar_id" Type="Decimal" Nullable="false" />
  <Property Name="bop_session_datetime" Type="DateTime" Nullable="false" />
  <Property Name="bop_language" Type="String" Nullable="false" MaxLength="2" />
  <Property Name="bop_status" Type="Decimal" Nullable="false" />
</EntityType>

<EntityType Name="bop_webinar_submission">
  <Key>
    <PropertyRef Name="bop_submission_id" />
  </Key>
  <Property Name="bop_submission_id" Type="Decimal" Nullable="false" />
  <Property Name="bop_user_name" Type="String" Nullable="false" MaxLength="100" />
  <Property Name="bop_id_type" Type="String" Nullable="false" MaxLength="10" />
  <Property Name="bop_id_no" Type="String" Nullable="false" MaxLength="12" />
  <Property Name="bop_mobile_no" Type="String" Nullable="false" MaxLength="15" />
  <Property Name="bop_email_address" Type="String" Nullable="false" MaxLength="50" />
  <Property Name="bop_find_source" Type="String" MaxLength="200" />
  <Property Name="bop_consent_agreed" Type="Decimal" Nullable="false" />
  <Property Name="bop_bo_branchcode" Type="String" Nullable="false" MaxLength="10" />
  <Property Name="bop_createstmp" Type="DateTime" />
  <Property Name="bop_ip_address" Type="String" MaxLength="50" />
</EntityType>

<EntityType Name="bop_webinar_user_session">
  <Key>
    <PropertyRef Name="bop_user_submission_id" />
    <PropertyRef Name="bop_session_id" />
  </Key>
  <Property Name="bop_user_submission_id" Type="Decimal" Nullable="false" />
  <Property Name="bop_session_id" Type="Decimal" Nullable="false" />
</EntityType>







<EntitySetMapping Name="bop_webinar">
  <EntityTypeMapping TypeName="YourModel.bop_webinar">
    <MappingFragment StoreEntitySet="bop_webinar">
      <ScalarProperty Name="bop_webinar_id" ColumnName="bop_webinar_id" />
      <ScalarProperty Name="bop_title_en" ColumnName="bop_title_en" />
      <ScalarProperty Name="bop_title_bm" ColumnName="bop_title_bm" />
      <ScalarProperty Name="bop_title_ch" ColumnName="bop_title_ch" />
      <ScalarProperty Name="BOP_CREATEBY" ColumnName="BOP_CREATEBY" />
      <ScalarProperty Name="BOP_CREATESTMP" ColumnName="BOP_CREATESTMP" />
      <ScalarProperty Name="BOP_LASTEDITBY" ColumnName="BOP_LASTEDITBY" />
      <ScalarProperty Name="BOP_LASTEDITSTMP" ColumnName="BOP_LASTEDITSTMP" />
      <ScalarProperty Name="BOP_APPROVER1" ColumnName="BOP_APPROVER1" />
      <ScalarProperty Name="BOP_APPROVESTMP1" ColumnName="BOP_APPROVESTMP1" />
      <ScalarProperty Name="BOP_APPROVER2" ColumnName="BOP_APPROVER2" />
      <ScalarProperty Name="BOP_APPROVESTMP2" ColumnName="BOP_APPROVESTMP2" />
      <ScalarProperty Name="BOP_PENDID" ColumnName="BOP_PENDID" />
      <ScalarProperty Name="bop_status" ColumnName="bop_status" />
    </MappingFragment>
  </EntityTypeMapping>
</EntitySetMapping>

<EntitySetMapping Name="bop_webinar_session">
  <EntityTypeMapping TypeName="YourModel.bop_webinar_session">
    <MappingFragment StoreEntitySet="bop_webinar_session">
      <ScalarProperty Name="bop_session_id" ColumnName="bop_session_id" />
      <ScalarProperty Name="bop_webinar_id" ColumnName="bop_webinar_id" />
      <ScalarProperty Name="bop_session_datetime" ColumnName="bop_session_datetime" />
      <ScalarProperty Name="bop_language" ColumnName="bop_language" />
      <ScalarProperty Name="bop_status" ColumnName="bop_status" />
    </MappingFragment>
  </EntityTypeMapping>
</EntitySetMapping>

<EntitySetMapping Name="bop_webinar_submission">
  <EntityTypeMapping TypeName="YourModel.bop_webinar_submission">
    <MappingFragment StoreEntitySet="bop_webinar_submission">
      <ScalarProperty Name="bop_submission_id" ColumnName="bop_submission_id" />
      <ScalarProperty Name="bop_user_name" ColumnName="bop_user_name" />
      <ScalarProperty Name="bop_id_type" ColumnName="bop_id_type" />
      <ScalarProperty Name="bop_id_no" ColumnName="bop_id_no" />
      <ScalarProperty Name="bop_mobile_no" ColumnName="bop_mobile_no" />
      <ScalarProperty Name="bop_email_address" ColumnName="bop_email_address" />
      <ScalarProperty Name="bop_find_source" ColumnName="bop_find_source" />
      <ScalarProperty Name="bop_consent_agreed" ColumnName="bop_consent_agreed" />
      <ScalarProperty Name="bop_bo_branchcode" ColumnName="bop_bo_branchcode" />
      <ScalarProperty Name="bop_createstmp" ColumnName="bop_createstmp" />
      <ScalarProperty Name="bop_ip_address" ColumnName="bop_ip_address" />
    </MappingFragment>
  </EntityTypeMapping>
</EntitySetMapping>

<EntitySetMapping Name="bop_webinar_user_session">
  <EntityTypeMapping TypeName="YourModel.bop_webinar_user_session">
    <MappingFragment StoreEntitySet="bop_webinar_user_session">
      <ScalarProperty Name="bop_user_submission_id" ColumnName="bop_user_submission_id" />
      <ScalarProperty Name="bop_session_id" ColumnName="bop_session_id" />
    </MappingFragment>
  </EntityTypeMapping>
</EntitySetMapping>


